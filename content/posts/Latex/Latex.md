---
title: LaTeX mit TeX Live, LuaLaTeX, LyX und TeXstudio
description: Eine Einführung in modernes LaTeX – vom Editor bis zur PDF
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michael Hailer
tags:
  - LaTeX
  - TeX
  - Live
  - LyX
  - TeXstudio
  - LuaLaTeX
erstellt: 2025-06-30T13:01
geändert: 2025-06-30T18:20
---

# Einführung in LaTeX

## Was ist LaTeX?
**LaTeX** (ˈlaːtɛç] ist ein [plattformunabhängiges](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Plattformunabh%C3%A4ngigkeit "Plattformunabhängigkeit") und [freies Softwarepaket](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Freie_Software "Freie Software"), das die Benutzung des [Textsatzsystems](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Satz_\(Druck\) "Satz (Druck)") [TeX](https://de.wikipedia.org/api/rest_v1/page/mobile-html/TeX "TeX") mit Hilfe von [Makros](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Makro "Makro") vereinfacht. LaTeX ist eine [Auszeichnungssprache](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Auszeichnungssprache "Auszeichnungssprache") und ein [Dateiformat](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Dateiformat "Dateiformat"), um insbesondere Texte, die [mathematische Formeln](https://de.wikipedia.org/api/rest_v1/page/mobile-html/Formel "Formel")enthalten, zu schreiben und für den Druck oder die Bildschirmansicht zu formatieren.


Typische Anwendungsbereiche:

- wissenschaftliche Arbeiten
- technische Dokumentation
- Bücher, Vorträge, Gedichtbände
- rechtssichere PDFs mit Layoutkontrolle

---

## Warum LaTeX statt Word?

| LaTeX                            | Word                                |
| -------------------------------- | ----------------------------------- |
| Trennung von Inhalt & Layout     | Mischform von Layout + Inhalt       |
| Stabil für lange Dokumente       | Formatierungen können „verrutschen“ |
| Versionskontrolle möglich        | Binärformat, schlecht vergleichbar  |
| Bestens geeignet für Formeln     | Nur mit externen Plugins            |
| Automatisierbar (Makefiles etc.) | Meist manuelle Bedienung            |

---

## Setup auf meinem System

- **TeX Live 2025** (lokal installiert)
- **LuaLaTeX** als Engine (`lualatex`)
- **LyX** für WYSIWYG-Komfort
- **TeXstudio** für klassische .tex-Dateien
- **latexmk** + `.latexmkrc` für automatisiertes Kompilieren
- **Libertinus** als Standardschrift

---

## Beispielcode

```latex
\documentclass{article}

\usepackage{libertinus}
\usepackage[ngerman]{babel}
\usepackage{microtype}
\usepackage{hyperref}

\title{Meine erste LaTeX-Datei}
\author{Dr. Michi Hailer}
\date{\today}

\begin{document}
\maketitle

\section{Einleitung}
LaTeX trennt Inhalt und Form. Das ist gut.

\section{Formeln}
Eine berühmte Gleichung:
\[
e^{i\pi} + 1 = 0
\]

\end{document}
```

## Kompilierung

lualatex mein-dokument.tex
Oder in TeXstudio: ⌨️ auf den „PDF“‑Button klicken.

## Wichtige Pakete

libertinus → moderne Schrift
babel → Sprachunterstützung
microtype → bessere Typografie
hyperref → klickbare Links
biblatex + biber → Literaturverwaltung
csquotes, graphicx, cleveref → Format, Bilder, Referenzen

## Verzeichnisstruktur

projekt/
├── mein-dokument.tex
├── literatur.bib
├── figure1.pdf
├── mein-dokument.pdf

## Weiterführende Links

[Wikibooks Latex](https://de.wikibooks.org/wiki/LaTeX)
[Latex Tutorial](https://latex-tutorial.com/)
[TeX Stackexchange][def]

## Fazit

LaTeX ist mächtig, sauber, kontrolliert – und genau richtig, wenn man Wert auf hochwertige, reproducible PDFs legt.
Gerade in Kombination mit latexmk, LyX oder Emacs ist es ein nachhaltiges Werkzeug für technische und wissenschaftliche Texte.

[def]: https://tex.stackexchange.com/
