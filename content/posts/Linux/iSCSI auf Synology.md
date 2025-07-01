---
erstellt: 2025-06-30T17:47
geändert: 2025-06-30T18:20
---
# 🛡️ iSCSI-Backup mit Synology NAS, Timeshift und rsync (Linux)

Dieses Dokument beschreibt **Schritt für Schritt**, wie ein iSCSI-Laufwerk auf einer **Synology NAS** erstellt, formatiert, gemountet und anschließend mit **Timeshift** und **rsync** als Backupziel genutzt wird.

---

## 🔧 Voraussetzungen

- Synology NAS mit DSM (DiskStation Manager)
- iSCSI aktiviert und erreichbar im lokalen Netz
- Linux-Client (z. B. Linux Mint, Debian)
- Root-Zugriff
- `open-iscsi`, `lsscsi`, `parted`, `mkfs.ext4` auf dem Client installiert

---

## 🧱 1. iSCSI-Ziel auf der Synology einrichten

1. Melde dich an der NAS im **DSM-Webinterface** an.
2. Gehe zu: **Systemsteuerung > iSCSI Manager**
3. Klicke auf **Erstellen** und wähle:
   - **Name**: z. B. `backup-target`
   - **IQN** (automatisch generiert oder `iqn.2025-06.local.synology:backup`)
1. Aktiviere das Ziel, aber belasse es **ohne LUN** (wird im Anschluss erstellt).

---

## 💾 2. LUN erstellen

1. Gehe im iSCSI Manager auf **LUN erstellen**
2. Wähle **Dateibasierte LUN (empfohlen)** oder **Block-LUN** (für Performance)
3. Konfiguriere:
   - **Name**: z. B. `backup-lun`
   - **Größe**: z. B. `500GB`
   - **Speicherort**: Volume auswählen
   - **Zugeordnetes Ziel**: `backup-target`
4. Klicke auf **Erstellen** und **Zuweisen**

---

## 🌐 3. Linux-Client vorbereiten

### iSCSI installieren:

```bash
sudo apt install open-iscsi lsscsi
```

---

## 🔌 4. iSCSI-Verbindung zum Ziel herstellen

als Beispiel-IP für Deine Synology NAS wird hier 192.168.178.75 verwendet, bitte anpassen 

1. Ziel suchen:

```bash
sudo iscsiadm --mode discovery --type sendtargets --portal 192.168.178.75
```

2. Verbindung aufbauen:

```bash
sudo iscsiadm --mode node --targetname iqn.2025-06.local.synology:backup --portal 192.168.178.75 --login
```

3. Aktivieren beim Boot:

```bash
sudo iscsiadm --mode node --targetname iqn.2025-06.local.synology:backup --portal 192.168.178.75 --op update --name node.startup --value automatic
```

4. Gerät identifizieren:

```bash
lsblk
```

Das neue Laufwerk erscheint als `/dev/sdX` 
(z. B. `/dev/sdb`)

---

## 🧽 5. Partitionieren und formatieren

```bash
sudo parted /dev/sdX mklabel gpt
sudo parted -a optimal /dev/sdX mkpart primary ext4 0% 100%
sudo mkfs.ext4 -L BACKUP /dev/sdX1
```

---

## 📂 6. Mountpoint einrichten

```bash
sudo mkdir -p /mnt/iscsi
sudo blkid           # finde UUID heraus
```

In `/etc/fstab` eintragen:

```fstab
UUID=deine-uuid /mnt/iscsi ext4 nofail,_netdev 0 2
```

Dann mounten:

```bash
sudo mount /mnt/iscsi
```

---

## 📦 7. Backup-Script mit Timeshift + rsync

```bash
#!/bin/bash
set -e

# Timeshift: System-Backup auf iSCSI
sudo timeshift --create --comments "Automatisches Backup" --tags D --snapshot-device /mnt/iscsi

# rsync: Home-Backup (z. B. für /home/<user-name>)
rsync -avh --delete ~/mnt/iscsi/home/<user-name>/

echo "Backup abgeschlossen: $(date)" | systemd-cat -t backup-script
```

Speichern unter z. B. `~/bin/backup-notebook-gui.sh`

---

## 🕒 8. Optional: systemd-Timer zur Automatisierung

Erstelle folgende zwei Dateien in `~/.config/systemd/user/`:

### `backup-notebook.service`

```ini
[Unit]
Description=Notebook Backup auf NAS

[Service]
ExecStart=~/bin/backup-notebook-gui.sh
```

### `backup-notebook.timer`

```ini
[Unit]
Description=Backup täglich um 01:00

[Timer]
OnCalendar=*-*-* 01:00:00
Persistent=true

[Install]
WantedBy=timers.target
```

Dann aktivieren mit:

```bash
systemctl --user daemon-reexec
systemctl --user enable --now backup-notebook.timer
```

---

## ✅ Fazit

Mit dieser Konfiguration ist dein System **sicher**, die **Backups laufen automatisiert** und das iSCSI-Target bleibt **zentral und flexibel erweiterbar** auf deiner Synology NAS.

---
mit ❤️ zusammengestellt und programmiert von Michael 