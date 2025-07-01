---
title: LibreWolf – Der datenschutzfreundlichste Firefox
description: Warum ich LibreWolf statt Firefox oder Chrome nutze und wie ich ihn konfiguriert habe
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michi Hailer
tags:
  - LibreWolf
  - Firefox
  - Browser
  - Datenschutz
  - Hardening
erstellt: 2025-06-30T13:51
geändert: 2025-06-30T18:20
---

# LibreWolf – Der datenschutzfreundlichste Firefox

## Was ist LibreWolf?

**LibreWolf** ist ein **fork von Firefox**, der sich komplett auf **Datenschutz, Sicherheit und Unabhängigkeit** konzentriert. Er wird regelmäßig aktualisiert, ist quelloffen, werbefrei und **standardmäßig gehärtet**.

---

## Vorteile gegenüber Firefox und Chrome

| Merkmal                 | LibreWolf       | Firefox           | Chrome               |
|-------------------------|------------------|--------------------|-----------------------|
| Telemetrie deaktiviert  | ✅                | ❌ (Opt-out)        | ❌ (Google Tracking)   |
| Google als Suchmaschine| ❌                | ✅                  | ✅ (Zwang)            |
| Autoupdates             | ❌ (kontrolliert) | ✅                  | ✅                    |
| Erweiterungen           | ✅ alle WebExt    | ✅                  | ✅                    |
| Werbung in Startseite  | ❌                | ✅                  | ✅                    |
| User.js Hardening       | ✅ integriert     | ❌                  | ❌                    |
| DRM (Widevine)          | ❌ optional       | ✅                  | ✅                    |

---

## Mein Setup

Ich nutze LibreWolf als meinen **Hauptbrowser** unter Linux Mint, da er:

- keine Verbindungen zu Mozilla oder Google aufbaut
- keinerlei Telemetrie sendet
- alle Sicherheitseinstellungen bereits vorkonfiguriert hat
- Werbetracking von Haus aus blockiert
- alle meine Firefox-Erweiterungen unterstützt

---

## Installation unter Linux Mint

```bash
sudo apt install wget gnupg lsb-release
echo 'deb [signed-by=/usr/share/keyrings/librewolf.gpg] https://deb.librewolf.net stable main' | sudo tee /etc/apt/sources.list.d/librewolf.list
wget https://deb.librewolf.net/keyring.gpg -O- | sudo gpg --dearmor -o /usr/share/keyrings/librewolf.gpg
sudo apt update
sudo apt install librewolf
```

---

## Erweiterungen

Ich verwende:

- **uBlock Origin**
- **Bitwarden**
- **ClearURLs**
- **Decentraleyes**
- **Dark Reader**
- **LocalCDN**
- **Firefox Multi-Account Containers**
- **User-Agent Switcher and Manager**

---

## Suchmaschine

Meine Standard-Suchmaschine ist **Startpage**, alternativ **DuckDuckGo** oder **Searx**. Ich habe Google komplett entfernt.

---

## Einstellungen (Hardening)

LibreWolf bringt bereits eine `user.js` mit – aber ich habe zusätzlich angepasst:

```json
privacy.resistFingerprinting = true
privacy.firstparty.isolate = true
network.cookie.cookieBehavior = 1
```

- **Kein WebRTC-Leak**
- **Kein Canvas-Fingerprint**
- **DoH deaktiviert** (nutze DoT über die FRITZ!Box)
- **Keine Push-Benachrichtigungen**

---

## Keine Sync-Funktion?

Stimmt – **LibreWolf verzichtet bewusst auf Firefox Sync**. Ich nutze stattdessen:

- **Syncthing** für das Syncen des Profils
- oder ein dediziertes Firefox-Profil mit `firefox -P`

---

## Geringerer RAM-Verbrauch

LibreWolf ist durch das Entfernen vieler Hintergrundprozesse spürbar **ressourcenschonender** als Firefox oder Chromium – ideal für mein Notebook (Acer Aspire 5).

---

## Nachteile?

- Kein automatisches Update via Flatpak oder PPA
- Kein DRM (Netflix etc.) ohne manuelles Nachrüsten
- Kein Firefox-Sync (aber gewollt)
- Etwas nerdiger – aber genau das ist gewollt

---

## Fazit

LibreWolf ist mein Browser der Wahl, weil er:

- **keine Daten sammelt**
- **von Grund auf auf Sicherheit und Datenschutz ausgelegt ist**
- **offen und transparent entwickelt wird**

Gerade in Zeiten von zentralisiertem Tracking und Cloud-Zwang ist LibreWolf ein starkes Zeichen für digitale **Autonomie** und **Privatsphäre**.

---

## Link
[**Librewolf**](https://librewolf.net/)

