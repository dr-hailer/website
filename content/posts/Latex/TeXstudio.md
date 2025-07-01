---
title: TeXstudio – Der klassische LaTeX-Editor für Profis
description: Effizienter arbeiten mit LaTeX durch integrierte Vorschau, Syntaxhilfe, und Build-Tools
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michi Hailer
tags:
  - LaTeX
  - TeXstudio
  - LuaLaTeX
  - latexmk
  - TexLive
erstellt: 2025-06-30T13:17
geändert: 2025-06-30T18:20
---

# TeXstudio – Der klassische LaTeX-Editor für Profis

## Was ist TeXstudio?

**Texstudio** ist ein klassischer, leistungsfähiger LaTeX-Editor mit Fokus auf:

- komfortable Quelltextbearbeitung
- integrierte PDF-Vorschau
- Syntax-Highlighting
- automatische Komplettierung
- Build-Integration (z. B. `latexmk`)

Er ist besonders geeignet, wenn man präzise Kontrolle über den LaTeX-Code behalten will, aber nicht auf Komfort verzichten möchte.

---

## Mein Setup

Ich verwende:

- **TeXstudio 4.x** (aus dem PPA oder als .AppImage)
- **LuaLaTeX** als bevorzugte Engine
- **TeX Live 2025** als LaTeX-Distribution
- **latexmk** als Build-Tool über `.latexmkrc`
- **Libertinus** als Hauptschriftart

---

## Vorteile von TeXstudio

| Feature                          | Nutzen                                 |
|----------------------------------|----------------------------------------|
| Integrierte PDF-Vorschau         | Änderungen sofort sichtbar             |
| Auto-Vervollständigung           | Schnelleres Schreiben von Befehlen     |
| Projektstruktur / Gliederung     | Übersicht bei langen Dokumenten        |
| LaTeX-Wiki-Links & Doku-Hilfe    | Hilfreich beim Nachschlagen            |
| Fehleranzeige im Build-Log       | Probleme leichter identifizieren       |
| Synctex-Unterstützung            | Klick im PDF springt zur .tex-Zeile    |

---

## Build in TeXstudio

### 🔧 `.latexmkrc` Beispiel

Erstelle (oder bearbeite) in deinem Home-Verzeichnis die Datei `.latexmkrc`:

```perl
$pdflatex = 'lualatex -interaction=nonstopmode -synctex=1';
$pdf_mode = 1;
$bibtex_use = 2;
$pdf_previewer = 'start evince';
```

Alternativ kannst du auch `zathura`, `okular` oder `mupdf` eintragen, je nach deinem bevorzugten PDF-Viewer.

---

### 🛠 Build-Befehl in TeXstudio einrichten

1. Menü `Optionen → TeXstudio konfigurieren`
2. Reiter `Erzeugen`
3. Unter **Benutzerbefehle** einfügen:

```bash
latexmk -pdf -pdflatex=lualatex %.tex
```

4. Anschließend im Hauptmenü:
   - Reiter `Erzeugen`
   - Dropdown ganz oben: Wähle deinen neuen `latexmk`-Befehl als Standard

So wird bei jedem Kompilieren `lualatex` mit `latexmk` verwendet.

---

### Tastenkürzel (Auswahl)

| Shortcut             | Funktion                       |
|----------------------|--------------------------------|
| `F5`                 | Kompilieren                    |
| `F7`                 | Nur PDF erzeugen               |
| `Ctrl + Space`       | Auto-Vervollständigung         |
| `Ctrl + Click (PDF)` | Springt zur zugehörigen Zeile  |
| `Ctrl + Shift + F`   | Alle Dateien durchsuchen       |

---

### Weitere Tipps

- Aktiviere automatische Rechtschreibprüfung unter `Optionen → Einstellungen → Rechtschreibung`
- Nutze Makros für eigene Umgebungen oder häufig genutzte Formeln
- Richte Projekte mit Unterordnern ein (`kapitel1/`, `bilder/`, `bibliographie/`)

---

### Vergleich zu LyX

| TeXstudio             | LyX                            |
|-----------------------|---------------------------------|
| reiner Quelltext      | WYSIWYM-Editor                  |
| volle LaTeX-Kontrolle | eingeschränkter Low-Level-Zugriff |
| Git-kompatibel        | `.lyx`-Dateien schwer vergleichbar |
| schneller Einstieg    | visuell-intuitiver Einstieg     |

---

## Links

- [TeXstudio Website](https://www.texstudio.org)
- [TeXstudio auf GitHub](https://github.com/texstudio-org/texstudio)
- [TeX Live 2025](https://www.tug.org/texlive/)

---

## Fazit

Mit `latexmk` und `lualatex` hast du in TeXstudio einen modernen, stabilen und komfortablen LaTeX-Workflow.  
Gerade für technisch anspruchsvolle Dokumente oder wissenschaftliches Schreiben ist das Setup ideal.
