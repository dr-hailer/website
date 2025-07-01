---
title: privacy.sexy – Automatisierte Datenschutz-Härtung für Windows, macOS und Linux
description: Ein modernes, quelloffenes Tool zur datenschutzfreundlichen Systemkonfiguration mit Automatisierung und Transparenz
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michi Hailer
tags:
  - privacy.sexy
  - Datenschutz
  - Hardening
  - Windows
  - Linux
  - macOS
  - Sicherheit
erstellt: 2025-06-30T14:01
geändert: 2025-06-30T18:20
---

# privacy.sexy – Automatisierte Datenschutz-Härtung für Windows, macOS und Linux

[privacy.sexy](https://privacy.sexy) ist ein modernes, quelloffenes Tool zur **automatisierten Systemhärtung**, das sich ganz der **Datensparsamkeit, Deaktivierung von Telemetrie** und **Abschaltung unnötiger Dienste** widmet.

Es eignet sich hervorragend für:

- **Datenschutz-Neulinge** (einfache Oberfläche)
- **Power-User** (CLI, Skripte, Modulstruktur)
- **Multiplattform-Systeme** (Win/macOS/Linux)

---

## Grundprinzip

Statt alles selbst mit Skripten zu konfigurieren, kann man in privacy.sexy:

- Maßnahmen aus einer **grafischen Oberfläche** auswählen
- ein maßgeschneidertes Skript generieren lassen
- es sofort ausführen oder manuell prüfen
- es als Backup-Konfiguration speichern

💡 Alles geschieht lokal, **ohne Cloud-Abhängigkeit oder Telemetrie**.

---

## Plattformen & Features

### ✅ Unterstützt:

- **Windows 10 & 11**
- **macOS (Intel & M1/M2)**
- **Linux (Debian/Ubuntu/Arch)**

### 🔧 Typische Maßnahmen:

- **Windows**: Deaktivieren von Cortana, OneDrive, Telemetrie, Feedback-Diensten, Werbung
- **macOS**: Disable Siri, iCloud Drive, Standortdienste, Autoupdates
- **Linux**: DNS über DoT konfigurieren, journald-Einstellungen, sysctl-Hardening

---

## Vorteile gegenüber herkömmlichen Hardening-Skripten

| Merkmal                         | privacy.sexy         | manuelle Skripte   |
|---------------------------------|-----------------------|---------------------|
| Web-GUI zur Auswahl             | ✅                    | ❌                  |
| Transparent und nachvollziehbar| ✅                    | teils schwer lesbar |
| Plattformübergreifend           | ✅                    | ❌                  |
| Automatisches Undo möglich      | ✅                    | ❌                  |
| Open Source (MIT)               | ✅                    | ✅/❌ je nach Quelle |

---

## Bedienung

1. Öffne [privacy.sexy](https://privacy.sexy) im Browser
2. Wähle dein System (z. B. Windows)
3. Setze Haken bei gewünschten Modulen (z. B. Disable Cortana, Block Telemetry)
4. Klick auf „Show Script“
5. Speichere oder führe es direkt aus

Du kannst die Konfiguration auch **als YAML exportieren** und später erneut laden.

---

## Beispiel: Windows 11 Härtung

- Entferne Werbung und empfohlene Apps
- Blockiere Telemetrie mit Hosts-Dateien
- Deaktiviere OneDrive, Cortana, Bing-Integration
- Setze `Windows Defender` auf benutzerfreundlich ohne Cloud-Upload

```powershell
# Beispielscriptauszug:
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Search" /v BingSearchEnabled /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Search" /v CortanaConsent /t REG_DWORD /d 0 /f
```

---

## Was ich besonders schätze

- Die Kombination aus **grafischer Auswahl** und **vollständiger Kontrolle**
- Die Möglichkeit, **Undo-Skripte automatisch zu generieren**
- Die sinnvolle Trennung von **Hardening, Privacy, Performance und Netzwerk**
- Die **lokale Ausführung ohne Cloudbindung**

---

## Integration in mein Setup

- Für Windows-Gäste in meiner virtualisierten Testumgebung
- Für Freunde & Familie, die einfache Privacy-Voreinstellungen wollen
- Zum Vergleich von Windows-Telemetrie mit LibreWolf/Firefox-Voreinstellungen
- Testweise auf meinem Linux Mint durch sysctl- und journald-Tuning

---

## Fazit

📦 **privacy.sexy ist das moderne, modulare Pendant zum klassischen privacy-handbuch.de.**

Es macht Datenschutz für Endnutzer **zugänglich, transparent und rückverfolgbar**. Ideal für:

- 🧑‍💻 Technikbegeisterte
- 👩‍🏫 IT-Coaches
- 🛡️ Security-Admins

…und für alle, die **ihr System lieber selbst kontrollieren als von Microsoft, Apple oder Google „übernehmen“ zu lassen**.

---

## Link
[privacy.sexy - Maximize Your Privacy and Security](https://privacy.sexy/)

