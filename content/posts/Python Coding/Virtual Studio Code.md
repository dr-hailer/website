---
title: Visual Studio Code – Mein optimiertes Setup
description: Wie ich VS Code als zentrale Entwicklungsumgebung für Markdown, Python, LaTeX und KI-Projekte verwende – mit perfektem Theme, Plugins und Struktur.
created: 2025-06-30
updated: 2025-06-30
author: Dr. Michi Hailer
tags:
  - VS Code
  - Markdown
  - Python
  - LaTeX
  - Jupyter
  - Theme
  - Zettelkasten
erstellt: 2025-06-30T13:49
geändert: 2025-06-30T18:20
---

# Visual Studio Code – Mein optimiertes Setup

## Warum VS Code?

Ich verwende  [** Visual Sudio Code **](https://code.visualstudio.com/Download)als zentrale Umgebung für:

- Python-Entwicklung (Miniconda, Jupyter, Ruff, Black)
- Markdown-Wissensarbeit (mit Nord-/Dracula-Theme)
- LaTeX-Projekte (LuaLaTeX, LaTeX Workshop)
- Obsidian-kompatible Markdown-Vaults
- Docker, YAML, Bash-Skripting
- alles rund um mein Prometheus-Projekt

---

## Fonts, Themes & Layout

- **Schriftart:** JetBrains Mono Nerd Font
- **Theme:** Dracula + Nord-Schwarz (angepasst)
- **Terminal:** GNOME Terminal mit powerlevel10k zsh
- **Icon Pack:** Material Icon Theme

### 🎨 Beispiel: settings.json (Ausschnitt)

```json
"editor.fontFamily": "'JetBrains Mono Nerd Font', monospace",
"editor.fontSize": 14,
"editor.lineHeight": 22,
"editor.cursorStyle": "line",
"workbench.colorTheme": "Dracula",
"workbench.iconTheme": "material-icon-theme",
"editor.guides.indentation": true
```

---

## Erweiterungen (Extensions)

| Kategorie       | Extensions                                    |
|------------------|-----------------------------------------------|
| Markdown         | Markdown All in One, Foam, Markdown Preview Enhanced |
| Python           | Python, Jupyter, Pylance, Black Formatter, Ruff |
| LaTeX            | LaTeX Workshop (LuaLaTeX, latexmk)            |
| YAML/Docker      | YAML, Docker, GitLens, .env                   |
| Codequalität     | Code Spell Checker, indent-rainbow            |
| Weiteres         | Continue, ChatGPT, Bracket Pair Colorizer 2   |

---

## Projektstruktur

Ich arbeite mit dedizierten Workspaces für:

- **`Prometheus/`** (KI-Wissensdatenbank, Qdrant, Ollama)
- **`paperless-ngx/`** (Dokumentenverarbeitung)
- **`Mein-Setup/`** (Markdown-Doku, GitHub-Projekt)

Mit `.code-workspace`-Dateien und individuellen `settings.json`.

---

## Besonderheiten

- **Markdown-Vault:** direkt mit Obsidian kompatibel (z. B. `~/Dokumente/ObsPrivat`)
- **Jupyter-Integration:** voll eingebunden mit Conda-Umgebungen
- **LaTeX:** LuaLaTeX über `latexmk`, Ausgaben im `build/`-Ordner
- **GitHub:** SSH-Zugang + GPG-Signierung, direkt in VS Code nutzbar
- **Continue + Ollama:** lokales KI-Modell für Codeunterstützung

---

## LaTeX Workshop Setup

```json
"latex-workshop.latex.recipes": [
  {
    "name": "LuaLaTeX",
    "tools": ["lualatexmk"]
  }
],
"latex-workshop.latex.tools": [
  {
    "name": "lualatexmk",
    "command": "latexmk",
    "args": [
      "-shell-escape",
      "-interaction=nonstopmode",
      "-file-line-error",
      "-pdf",
      "-pdflatex=lualatex",
      "%DOC%"
    ]
  }
],
"latex-workshop.latex.clean.fileTypes": [
  "*.aux", "*.log", "*.out", "*.fls", "*.fdb_latexmk", "*.synctex.gz", "*.toc"
]
```

---

## GitHub-Verknüpfung

- SSH-Key eingerichtet
- GPG-Signierung aktiv
- `Mein-Setup`-Repo verwaltet direkt Markdown-Dokumentation
- Änderungen bequem aus VS Code pushen

---

## Vorteile meines Setups

- **Optisch stimmig** (Nord/Dracula-Design)
- **Performance-optimiert** (Minimale Extensions)
- **Modular** (pro Projekt separater Workspace)
- **Markdown-zentriert**, ideal für Obsidian
- **KI-ready** (lokale Modelle, ChatGPT, Continue)

---

## Fazit

VS Code ist mein Hauptarbeitsplatz für alles, was editierbar ist – von Markdown über Python bis hin zu komplexen PDF-Workflows. Es ergänzt Emacs hervorragend: während Emacs tief integriert und skriptbar ist, bietet VS Code **Visibilität, Stabilität und Flexibilität**.

