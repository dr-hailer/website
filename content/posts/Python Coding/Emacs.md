---
title: Vanilla Emacs, Org-Mode und mein Setup
description: Warum ich mich für ein pures Emacs-Setup entschieden habe, wie ich Org-Mode verwende und welche Erweiterungen meinen Workflow unterstützen.
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michi Hailer
tags:
  - Emacs
  - Org-Mode
  - Vanilla
  - Zettelkasten
  - Plain Text
  - GNU
erstellt: 2025-06-30T13:39
geändert: 2025-06-30T18:20
---

# Vanilla Emacs, Org-Mode und mein Setup

---

[](https://de.wikipedia.org/w/index.php?title=Emacs&action=edit&section=0)

**Emacs** ist eine Familie von [Texteditoren](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Texteditor "Texteditor"). Die erste Emacs-Implementierung wurde von [Richard Stallman](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Richard_Stallman "Richard Stallman") (zusammen mit [Guy L. Steele, Jr.](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Guy_Lewis_Steele_junior "Guy Lewis Steele junior") und anderen) entwickelt. Besonders populär ist heute der **GNU Emacs**, der durch seine [Programmierschnittstelle](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Programmierschnittstelle "Programmierschnittstelle") in der [Programmiersprache](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Programmiersprache "Programmiersprache")[Emacs Lisp](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Emacs_Lisp "Emacs Lisp") mit beliebigen Erweiterungen ausgestattet werden kann. Es ist der Editor des [GNU/Linux-Projekts](https://de.wikipedia.org/api/rest_v1/page/mobile-html/GNU/Linux "GNU/Linux"). Es gibt aber auch noch eine Vielzahl von anderen Editoren, die zur Emacs-Familie zählen.

## Warum kein Doom oder Spacemacs?

Ich habe viele Distributionen ausprobiert – Doom, Spacemacs, etc. Am Ende war mir wichtig:

- **Vollständige Kontrolle** über meine Konfiguration
- **Minimale Abhängigkeiten** – kein komplexes Framework
- **Schneller Start**, kein overhead
- **Bessere Lernkurve**: Ich lerne Emacs *wirklich*, nicht nur Shortcuts

Deshalb nutze ich **Vanilla Emacs**, kompiliert aus Source (`emacs-30.1.90`) – mit persönlichem `init.el`.

---

## Mein Setup im Überblick

| Bereich               | Tool / Paket               |
|-----------------------|----------------------------|
| Editor                | Vanilla Emacs 30           |
| Datei-Explorer        | `dired`, `dired-subtree`   |
| Paketmanagement       | `use-package` + `MELPA`    |
| Theme                 | `modus-vivendi` (Nord-nah) |
| Schriftart            | `JetBrains Mono Nerd Font` |
| Org-Mode              | Standard + `org-modern`    |
| Kalender              | `org-agenda` + beorg (iOS) |
| Zitate / Literatur    | `citar`, `citar-denote`    |
| Zettelkasten          | `denote` (mit Markdown)    |
| Musik / Radio         | `emms`                     |
| Web                   | `eww`, `w3m`                |
| Shell                 | `eshell`, `vterm`          |

---

## Org-Mode

Ich verwende Org-Mode für:

- **Notizen** (schnell per `C-c c`)
- **Aufgaben / Agenda** mit `org-agenda`
- **Kalender-Synchronisation** via beorg + Nextcloud
- **Projektübersicht** (u. a. für das Prometheus-Projekt)
- **Meeting-Logs und wissenschaftliche Planungen**
- **Zettelkasten** via `denote` + Markdown

Beispiel für eine Aufgabenstruktur:

```org
* TODO Artikel zu Emacs schreiben
  DEADLINE: <2025-07-10>
  :PROPERTIES:
  :ID:       2e3f3174-aed0-442e-941d-setup-emacs
  :END:
  :LOGBOOK:
  CLOCK: [2025-06-30 Mo 10:00]--[2025-06-30 Mo 11:15] =>  1:15
  :END:
```

---

## Zettelkasten mit `denote`

Ich verwende [`denote`](https://protesilaos.com/emacs/denote/) mit **Markdown** und **YAML-Metadaten**, damit alles auch in Obsidian lesbar bleibt.

Beispiel:

```markdown
---
title: "Denote und Obsidian kombinieren"
date: 2025-06-28
tags: [zettelkasten, markdown, emacs]
---

Ich nutze Denote in Emacs mit Markdown-Dateien, die auch in Obsidian geöffnet werden können.
```

---

## Terminal-Setup

- **Prompt:** `powerlevel10k` in zsh
- **Terminal:** GNOME Terminal (Nord-Design)
- **Editor:** Emacs (außer bei SSH auf dem Server – da `nano`)
- **Conda:** manuell aktiviert, kein Autostart
- **Path angepasst für:** Emacs, Conda, TeX Live 2025, LM Studio

---

## Verwendung auf dem iPhone

- **beorg:** Kalender und Aufgaben mit org-Dateien über Nextcloud WebDAV
- **Nextcloud:** gehostet bei Hetzner
- **Markdown-Zettel:** per Syncthing mit Obsidian synchronisiert

---

## Fazit

Vanilla Emacs ist kein Rückschritt – es ist die pure Lehre. Ich habe die volle Kontrolle über mein Setup, kenne jede Zeile meiner `init.el`, und kann jederzeit auf neue Workflows reagieren.

Durch Kombination mit `denote`, `citar`, `org`, Nextcloud und Markdown entsteht ein vollständig quelloffener, portabler, datenschutzfreundlicher Arbeitsbereich.

Wenn du Emacs wirklich verstehen willst: Fang bei Vanilla an.

