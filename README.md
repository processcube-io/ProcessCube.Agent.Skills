# ProcessCube Claude Skills Marketplace

Skills für Claude Code zur Automatisierung von Release-Management und Changelog-Generierung bei ProcessCube-Komponenten.

## Verfügbare Skills

| Skill | Beschreibung | Auslöser |
|-------|-------------|----------|
| **release-process** | Erstellt Releases (Stable, Insiders, Development) mit Single-Branch-Workflow (nur `main`) | `/release-process` oder "Erstelle ein Release" |
| **changelog** | Erstellt oder aktualisiert ein Changelog aus der Git-Historie | `/changelog` oder "Erstelle ein Changelog" |

## Installation

### Alle Skills installieren

```bash
npx skills add processcube-io/ProcessCube.Claude.Development.Marketplace
```

### Einzelnen Skill installieren

```bash
npx skills add processcube-io/ProcessCube.Claude.Development.Marketplace --skill changelog
npx skills add processcube-io/ProcessCube.Claude.Development.Marketplace --skill release-process
```

### Manuelle Installation

1. Repository klonen:
   ```bash
   git clone https://github.com/processcube-io/ProcessCube.Claude.Development.Marketplace.git
   ```
2. Gewünschte Skills nach `.claude/skills/` im Zielprojekt kopieren:
   ```bash
   cp -r ProcessCube.Claude.Development.Marketplace/skills/release-process /path/to/project/.claude/skills/
   cp -r ProcessCube.Claude.Development.Marketplace/skills/changelog /path/to/project/.claude/skills/
   ```

## Updates

```bash
npx skills update
```

## Verwendung

Nach der Installation stehen die Skills in Claude Code als Slash-Commands zur Verfügung:

### Release erstellen

```
/release-process
```

Claude führt durch den Release-Prozess: Branch prüfen, Version bestimmen, Changelog generieren, Tag erstellen und pushen.

### Changelog generieren

```
/changelog
```

Claude erstellt oder aktualisiert das Changelog aus der Git-Historie, wahlweise für Anwender oder Entwickler.

## Autor

ProcessCube UG
