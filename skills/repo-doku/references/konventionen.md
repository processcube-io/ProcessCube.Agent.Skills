# Doku-Konventionen

## Sprache
- **Dokumentationssprache**: an der vorhandenen Doku / dem Projekt orientieren. Innerhalb eines
  Repos konsistent bleiben.
- **Code auf Englisch, Kommentare in der Doku-Sprache** (sofern das Projekt es so hält).
- Moderne, idiomatische Beispiele; keine Debug-Ausgaben in Beispielen, die als Produktionscode
  gelesen werden.

## Schreibstil
- Vorhandene Doku **fortschreiben** statt neu erfinden; Struktur und Ton der bestehenden README übernehmen.
- Beispiele aus **echtem Quellcode** ableiten (reale API, Optionen, Signaturen) — nichts erfinden.
- **Minimal-invasiv**: nur dokumentieren, was die neuen Commits/Features betreffen.
- Sauber, knapp, aussagekräftige Namen; DRY.

## Changelog
- Auf die **exakte Schreibweise** der Changelog-Datei im Repo achten (`Changelog.md` vs.
  `CHANGELOG.md` vs. `changelog.md`) und sie beibehalten.
- Changelog-Einträge aus **Nutzersicht** formulieren, nicht rein technisch.

## Diagramme (Mermaid)
- Wenn die Doku in MDX/Markdown gerendert wird, auf SSR-Kompatibilität achten.
- Robuste Syntax verwenden: Knoten-/Titel-Texte einfach halten, Subgraph-Titel quoten
  (`subgraph "Mein Titel"`), Sonderzeichen/Umlaute in Labels vermeiden, wenn der Renderer empfindlich ist.
- An die im Zielprojekt bereits verwendete (ggf. gepinnte) Mermaid-Version halten.

## Projekt-spezifische Konventionen
Viele Projekte haben eigene Regeln (Branding, erlaubte/verbotene Begriffe, Registry-URLs, Namens-
konventionen). Diese in einer Projekt-Datei (z.B. `CLAUDE.md`, `CONTRIBUTING.md`, Style-Guide)
nachschlagen und einhalten.

> **Beispiel ProcessCube®**: Produkt-/Markenname „ProcessCube®" (mit ®); „5Minds" → „ProcessCube®"
> nur bei Marken-/Produktnamen, **nicht** bei technischen Bezeichnern (`@5minds/`-npm-Pakete,
> `5minds/processcube_*`-Docker-Images, GitHub-URLs). Docker-Registry `marketplace.processcube.io`.
