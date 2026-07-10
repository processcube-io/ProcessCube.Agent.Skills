# Changelog

Alle nennenswerten Änderungen an den ProcessCube Agent Skills werden in dieser Datei dokumentiert (aus Nutzersicht).

## [1.0.0] - 2026-07-10

### Neue Features
- **release-process**: Skill zum Erstellen von Releases (Stable, Insiders, Development) nach Semantic Versioning mit Single-Branch-Workflow (nur `main`).
- **changelog**: Skill zum Erstellen und Aktualisieren von Changelogs aus der Git-Historie — wahlweise aus Nutzer- oder Entwicklersicht.
- **repo-doku**: Skill zum Erstellen und Aktualisieren der Repo-Dokumentation (README, bei größeren Projekten zusätzlich `DEVELOPMENT.md`) aus vorhandener Doku, Changelog, Git-Commits und Quellcode.
- Installation der Skills über `npx skills add processcube-io/ProcessCube.Agent.Skills` — für alle Skills, einzelne Skills oder gezielt für bestimmte Agenten (`openclaw`, `codex`, `claude-code`) ohne Rückfrage.

### Hinweise
- Die Skills folgen dem Agent Skills Open Standard und funktionieren mit kompatiblen Coding-Agenten (z.B. Claude Code, Codex, OpenClaw).
- Alle Skills und die Dokumentation sind auf Deutsch verfasst.
