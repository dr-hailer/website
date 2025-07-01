---
title: Betterbird + Proton Mail Bridge – Datenschutzfreundliche E-Mail auf dem Desktop
description: Warum ich Betterbird anstelle von Thunderbird nutze und wie ich damit meine Proton-Mail-Konten sicher verwalte
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michi Hailer
tags:
  - Betterbird
  - ProtonMail
  - Mailbridge
  - Thunderbird
  - E-Mail
  - Datenschutz
erstellt: 2025-06-30T13:54
geändert: 2025-06-30T18:20
---

# Betterbird + Proton Mail Bridge – Datenschutzfreundliche E-Mail auf dem Desktop

## Was ist Betterbird?

**Betterbird** ist ein Fork von Mozilla Thunderbird mit Fokus auf:

- **Stabilität**
- **Usability**
- **Barrierefreiheit**
- **Bugfixes und Verbesserungen**, die bei Thunderbird teils jahrelang unbearbeitet bleiben

Die Oberfläche ist identisch mit Thunderbird – aber unter der Haube läuft es **ruhiger, schneller und zuverlässiger**.

---

## Warum Betterbird statt Thunderbird?

| Merkmal                        | Betterbird     | Thunderbird     |
|-------------------------------|----------------|-----------------|
| Stabilitäts-Fokus             | ✅              | ❌              |
| Neuerungen & Patches schneller| ✅              | ❌              |
| Keine Experimente (z. B. Supernova UI) | ✅      | ❌              |
| Besserer Kalender/ICS-Support | ✅              | ❌              |
| Fewer random regressions      | ✅              | ❌              |
| Identische Addons             | ✅              | ✅              |

Ich hatte früher regelmäßig Ärger mit Thunderbird nach Updates – mit Betterbird ist das **Geschichte**.

---

## Proton Mail Bridge

Die **Proton Mail Bridge** ermöglicht es, verschlüsselte ProtonMail-Konten mit jedem IMAP/SMTP-Client zu verwenden.

### Vorteile

- Lokale PGP-Verschlüsselung bleibt erhalten
- Kein Web-Frontend notwendig
- Sicher durch lokale Tunnel (Bridge fungiert als Proxy)
- Funktioniert hervorragend mit Betterbird

---

## Einrichtungsschritte

### 1. Proton Mail Bridge starten

- Login mit ProtonMail-Konto
- Bridge erzeugt lokale IMAP-/SMTP-Zugänge (z. B. localhost:1143 / 1025)
- Pro Account ein Satz von Zugangsdaten

### 2. Betterbird Konto hinzufügen

- Manuell hinzufügen
- Server: `localhost`, Ports: wie von Bridge vorgegeben
- Benutzername/Passwort: in der Bridge sichtbar

---

## Addons in Betterbird

Ich verwende:

- **CardBook** (für Kontakte via CardDAV)
- **Lightning** (Kalender mit CalDAV über Nextcloud)
- **ImportExportTools NG**
- **uBlock Origin (Experimental)**

---

## Datenschutz und Kontrolle

- Kein zentralisiertes Google-Login
- Kein Sync mit Mozilla-Cloud
- GPG/MIME vollständig integriert
- Lokale Backups über Maildir oder `.mbox`

---

## Integration in mein Setup

- Nutze Betterbird auf dem **Notebook mit Linux Mint**
- Mailbridge läuft im Hintergrund (Autostart)
- Kalender und Kontakte via **Nextcloud CalDAV/CardDAV**
- Lokale GPG-Schlüssel für Signierung + Entschlüsselung

---

## Vorteile gegenüber Web-Frontend von Proton

| Feature                | Proton Web        | Betterbird + Bridge |
|------------------------|-------------------|----------------------|
| Offline-Nutzung        | ❌                | ✅                   |
| Lokale Backups         | ❌                | ✅                   |
| Integration mit Kalender/Kontakten | ❌        | ✅                   |
| Erweiterbarkeit (Addons)| ❌               | ✅                   |
| Tastatur-Workflow      | mittel            | ✅ (komplett steuerbar) |

---

## Fazit

Mit **Betterbird + Proton Mail Bridge** nutze ich meine Proton-Konten **sicher, schnell und unabhängig vom Browser**. Es ist eine perfekte Kombination aus:

- Datenschutz
- Lokaler Kontrolle
- Stabilität
- Erweiterbarkeit

Und das alles ohne die gelegentlichen Zickereien, die ich früher mit Thunderbird hatte.

---
## Links
[Betterbird. Simply better.](https://www.betterbird.eu/)

[Proton Mail](https://proton.me/de/mail)


