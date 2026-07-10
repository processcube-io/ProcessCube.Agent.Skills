# Changelog (Entwicklersicht)

Technische Änderungen an den ProcessCube Agent Skills (Commits, Dateien, Struktur).

## ✅ Stable v1.0.0 (10.07.2026)

*Erstes Release — alle Commits seit Projektbeginn*

### Neue Funktionen
- `20e25a2` docs: Verwendungstexte für release-process/changelog agent-agnostisch formulieren (#3)
- `168dc01` feat: repo-doku-Skill hinzufügen und Repo agent-agnostisch benennen (#2)
- `bf2e325` Add changelog skill as prerequisite step in release-process
- `76f6e92` Add a skill for changelog generation
- `e6d77bb` Add release skill

### Refactoring / Migration
- `8a18268` Migrate from plugin system to Agent Skills Open Standard
  - Umstellung vom bisherigen Plugin-System auf das Agent Skills Open Standard Format (`skills/<name>/SKILL.md`).
- `037d019` Add CLAUDE.md with project guidance for Claude Code

### Neue Dateien
- `skills/release-process/SKILL.md` — Release-Workflow (Stable/Insiders/Development, Single-Branch).
- `skills/changelog/SKILL.md` — Changelog-Generierung aus der Git-Historie.
- `skills/repo-doku/SKILL.md` — Repo-Dokumentation (README/DEVELOPMENT).
- `skills/repo-doku/references/doku-ziel.md`, `skills/repo-doku/references/konventionen.md` — gebündelte Referenzdateien für repo-doku.
- `CLAUDE.md` — Projekt-Guidance für Coding-Agenten.
- `README.md` — Installations- und Nutzungsanleitung (Deutsch).

### Geänderte Dateien
- `README.md` — Abschnitt „Für bestimmte Agenten ohne Rückfrage installieren" ergänzt (`--all`, `-a <agent>`, `-y`).

### Entfernte Dateien
- `LICENSE` — im Zuge der Umstrukturierung entfernt.
