---
title: Paperless-NGX als Docker-Setup auf meinem Server
description: Mein Setup für Dokumentenerfassung, OCR, Telegram-Bot und semantische Suche
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michi Hailer
tags:
  - Paperless-NGX
  - Docker
  - OCR
  - Backup
  - Dokumentenmanagement
---

---

## 🔧 Systemübersicht

Ich betreibe auf meinem **Debian 12 Beelink-Homeserver** eine vollständig dockerisierte Instanz von [Paperless-NGX](https://github.com/paperless-ngx/paperless-ngx). Ziel ist die **OCR-basierte Erfassung, Kategorisierung und Archivierung aller Dokumente**, inklusive Belegzuordnung, Suchfunktion und Automatisierung.

- **Server**: Beelink mit Debian 12 (headless)
- **CPU/RAM**: AMD, 32 GB RAM, 2 TB SSD
- **Docker-Stack**:
  - `paperless-ngx`
  - `postgres` (DB)
  - `redis` (Queue)
  - `gotenberg` + `tika` (OCR Parsing)
  - **Optional**: `SterlingPDF`, `Watchtower`

Die Weboberfläche ist lokal erreichbar unter:
http://192.168.178.111:8000

---

## 📦 Ordnerstruktur auf dem Host

/home/docker/paperless/
├── data/              # Dokumente & OCR
├── media/             # Uploads & Thumbnails
├── consume/           # Eingang (per Samba gemountet)
├── export/            # Exportierte PDFs
├── logs/              # Logging
└── docker-compose.yml

  ---

## 🧠 OCR & Verarbeitung

- Eingehende PDFs (per Scanner oder Bot) landen in consume/
- Paperless verarbeitet sie automatisch per OCR (Tesseract)
- Optional ergänzt durch SterlingPDF
- Volltext und Metadaten landen in PostgreSQL

---

## 📱 Telegram-Bot

Ich nutze einen Telegram-Bot, um

- PDFs direkt an den Server zu senden
- in consume/ zu speichern
- per telegram-send Status zu erhalten

---

## 🔁 Automatisierung

- Tägliches borg-Backup (Daten + DB)
- Wöchentlicher borg check --verify-data
- systemd-timer für Imports
- watchtower für Container-Updates

---

## 🧪 Erweiterte Funktionen

- Delta-Import: nur neue Dateien (per source_file)
- SterlingPDF Split + Beleglogik
- Qdrant Vektorimport für semantische Suche (Ollama)
- PostgreSQL-Zugriff über DBeaver (192.168.178.111:15432)

---

🧾 Typischer Ablauf

1. Scan landet via Samba in consume/
2. OCR läuft automatisch
3. Dokument erscheint im Webinterface
4. Tagging & Export
5. Automatischer oder manueller Follow-Up

---

## 📌 Fazit

Paperless-NGX ist ein zentrales Werkzeug in meinem Setup – stabil, lokal, automatisiert. Gemeinsam mit SterlingPDF, Telegram-Bot, Delta-Import und Qdrant entsteht ein leistungsfähiges digitales Archivsystem – ohne Cloud, ohne Kompromisse.