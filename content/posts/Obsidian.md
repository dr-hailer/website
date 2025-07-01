---
title: Obsidian als zentrale Wissensdatenbank – mein Setup
description: Wie ich Obsidian als Markdown-basierte Zettelkasten-Lösung auf Notebook, Server und Mobilgeräten nutze – mit Sync und Struktur.
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michi Hailer
tags:
  - Obsidian
  - Zettelkasten
  - Markdown
  - Sync
  - Syncthing
  - iPhone
  - Boox
erstellt: 2025-06-30T13:42
geändert: 2025-06-30T18:20
---

# Obsidian als zentrale Wissensdatenbank – mein Setup

**Obsidian** ist eine Software zur Erstellung und Organisation von [Notizen](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Notiz "Notiz") im [Markdown](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Markdown "Markdown")-Format, die für den persönlichen und kommerziellen Gebrauch kostenlos ist.
Obsidian eignet sich als Wissensdatenbank speziell für das persönliche Wissensmanagement und als eine Software zur Erstellung von Notizen, die mit Markdown Dateien arbeitet. 
Sie ermöglicht es Benutzern, interne Links für Notizen zu erstellen und die Verbindungen dann als Diagramm zu visualisieren. 
Obsidian wurde entwickelt, um Benutzern zu helfen, ihre Gedanken und ihr Wissen auf eine flexible, nicht-lineare Weise zu organisieren und zu strukturieren.
---

## Warum Obsidian?

Ich habe mich für **Obsidian** entschieden, weil es:

- mit **echten Markdown-Dateien** arbeitet
- **lokal läuft**, ohne Cloud-Zwang
- **plattformübergreifend** funktioniert (Linux, iOS, Android)
- **extrem erweiterbar** ist (Community-Plugins)
- **visuell ansprechend**, aber technisch solide ist

---

## Mein Vault: `ObsPrivat`

- Speicherort: `~/Dokumente/ObsPrivat`
- Versioniert mit GitHub (öffentliches Repo: `Mein-Setup`)
- Klar strukturierte Ordner:
  - `01_Inbox`
  - `02_Notizen`
  - `03_Begriffe`
  - `04_Zitate`
  - `05_Themen`
  - `06_Texte`
  - `07_Projekte`
  - `99_Archiv`

---

## Templates

Ich verwende eigene Templates, z. B.:

- Tagesnotiz
- Wochenübersicht
- Zitat
- Begriff
- Frage
- Prompt
- Rezept
- Ereignis
- Allgemeine Notiz

Die Templates nutzen YAML-Metadaten zur besseren Filterbarkeit.

Beispiel:

```markdown
---
title: "Was ist ein LLM?"
tags: [begriff, KI]
created: 2025-06-30
---

# Was ist ein LLM?

Ein LLM ist ein Large Language Model...
```

---

## Endgeräte und Sync

| Gerät                     | Methode                   | Bemerkung                            |
|---------------------------|---------------------------|--------------------------------------|
| Linux-Notebook            | native Obsidian App       | Vault: `~/Dokumente/ObsPrivat`       |
| Beelink-Homeserver        | Obsidian im Flatpak       | Schreibgeschützt / Archivfunktion    |
| iPhone                    | Obsidian Mobile           | Syncthing + Obsidian-Sync (Fallback) |
| Onyx Boox Note Air 4C     | Syncthing + Markdown-App  | Nur Lesezugriff oder PDF             |

### 🔁 Sync-Methode

Ich synchronisiere das Vault via:

- **Syncthing** (primär)
- **Obsidian Sync** (nur als Backup-Fallback aktiviert)

Dateien werden konfliktfrei über UUIDs und Metadaten gepflegt.

---

## Markdown-Vorschau in VS Code

Das Vault ist auch in VS Code integriert:

- `.vscode/settings.json` für Vorschau im Nord-Stil
- Markdown CSS-Stil angepasst
- `continue`, `foam`, `Markdown Preview Enhanced` aktiv

---

## Erweiterungen (Plugins)

Aktiv genutzt:

- **Calendar**
- **Templater**
- **QuickAdd**
- **Tag Wrangler**
- **Markdown Table Editor**
- **Advanced Tables**
- **Dataview** (für YAML-Auswertung)
- **Custom CSS**

---

## Nutzung mit Emacs

Ich verknüpfe das Vault zusätzlich mit `denote` in Emacs:

- alle Dateien `.md`
- YAML-Metadaten kompatibel mit Obsidian
- Zugriff über `denote-explore`, `citar`, `org-cite` etc.
- alles lesbar & editierbar auf Mobilgerät

---

## Einsatzszenarien

- **Tägliche Journaleinträge**
- **Projektplanung & Notizen**
- **Texte / Manuskripte**
- **Zitate und Quellen**
- **Recherche-Skizzen**
- **Fechsungen und Vorträge**
- **KI-Projekt „Prometheus“**

---

## Datenschutz

Da alle Daten lokal in Markdown liegen:

- Kein Vendor Lock-in
- Kein Cloud-Zwang
- Vollständige Kontrolle
- Versionskontrolle über Git möglich

---

## Fazit

Obsidian ist für mich das **Herzstück meiner digitalen Wissensarbeit**. In Kombination mit Emacs, Syncthing, Git und Markdown entsteht eine hochgradig portable, datenschutzfreundliche, zukunftssichere Zettelkasten-Umgebung.

---
## Link
[Obsidian - Sharpen your thinking](https://obsidian.md/)

