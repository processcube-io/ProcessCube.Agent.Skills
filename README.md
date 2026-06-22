# ProcessCube Agent Skills

Skills zur Automatisierung von Entwickler-Workflows wie Release-Management, Changelog-Generierung und Dokumentation. Die Skills folgen dem Agent Skills Open Standard und funktionieren mit kompatiblen Coding-Agenten (z.B. Claude Code, Codex, OpenClaw).

## Verfügbare Skills

| Skill | Beschreibung | Auslöser |
|-------|-------------|----------|
| **release-process** | Erstellt Releases (Stable, Insiders, Development) mit Single-Branch-Workflow (nur `main`) | `/release-process` oder "Erstelle ein Release" |
| **changelog** | Erstellt oder aktualisiert ein Changelog aus der Git-Historie | `/changelog` oder "Erstelle ein Changelog" |
| **repo-doku** | Erstellt/aktualisiert die Doku (README, ggf. DEVELOPMENT) im Quell-Repo aus Commits, Changelog und Quellcode | `/repo-doku` oder "Aktualisiere das README" |

## Installation

### Alle Skills installieren

```bash
npx skills add processcube-io/ProcessCube.Agent.Skills
```

### Einzelnen Skill installieren

```bash
npx skills add processcube-io/ProcessCube.Agent.Skills --skill changelog
npx skills add processcube-io/ProcessCube.Agent.Skills --skill release-process
npx skills add processcube-io/ProcessCube.Agent.Skills --skill repo-doku
```

### Manuelle Installation

1. Repository klonen:
   ```bash
   git clone https://github.com/processcube-io/ProcessCube.Agent.Skills.git
   ```
2. Gewünschte Skills nach `.claude/skills/` im Zielprojekt kopieren:
   ```bash
   cp -r ProcessCube.Agent.Skills/skills/release-process /path/to/project/.claude/skills/
   cp -r ProcessCube.Agent.Skills/skills/changelog /path/to/project/.claude/skills/
   cp -r ProcessCube.Agent.Skills/skills/repo-doku /path/to/project/.claude/skills/
   ```

## Updates

```bash
npx skills update
```

## Verwendung

Nach der Installation stehen die Skills im Coding-Agenten als Slash-Commands zur Verfügung (bzw. werden bei `repo-doku` automatisch über die Beschreibung erkannt):

### Release erstellen

```
/release-process
```

Der Agent führt durch den Release-Prozess: Branch prüfen, Version bestimmen, Changelog generieren, Tag erstellen und pushen.

### Changelog generieren

```
/changelog
```

Der Agent erstellt oder aktualisiert das Changelog aus der Git-Historie, wahlweise für Anwender oder Entwickler.

### Doku im Repo erstellen

```
/repo-doku
```

Der Agent wertet vorhandene Doku, Changelog, Git-Commits seit dem letzten Doku-Stand und den Quellcode aus und aktualisiert das README (bei größeren Projekten zusätzlich `DEVELOPMENT.md`) minimal-invasiv. Ist die Doku bereits aktuell, wird bewusst nichts geändert.

## Autor

ProcessCube UG
