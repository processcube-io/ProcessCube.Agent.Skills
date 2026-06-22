# Doku-Ziel und Umfang wählen

## README.md vs. README.md + DEVELOPMENT.md

| Projekt-Typ | Doku-Ziel | Grund |
|---|---|---|
| Bibliothek / Client / SDK | nur `README.md` | Nutzung der öffentlichen API steht im Vordergrund |
| CLI / Tool | nur `README.md` | Installation, Befehle, Beispiele |
| Kleine Anwendung / Service | nur `README.md` | Überblick + Setup genügt |
| Größere Anwendung / Plattform / Engine | `README.md` **+** `DEVELOPMENT.md` | Nutzer- und Entwicklerdoku trennen |

## Was ins README gehört
- Kurzbeschreibung: was das Projekt ist und löst
- Installation / Einbindung
- Schnellstart mit einem minimalen, lauffähigen Beispiel
- Öffentliche API / wichtigste Befehle (aus dem Quellcode verifiziert)
- Konfiguration / Optionen mit Defaults
- Authentifizierung/Voraussetzungen, falls relevant
- Lizenz

## Was in eine DEVELOPMENT.md gehört (nur größere Projekte)
- Architektur-Überblick
- Erweiterungspunkte / Plugin-System
- Domänen-spezifische Konzepte (z.B. BPMN-Elemente bei einer Workflow-Engine)

**Nicht** in die übernehmbare Doku: rein interne Details (IoC-Verdrahtung, Testarchitektur,
interne Build-Interna), die für Nutzer der Doku keinen Wert haben.

## Umfang
- An der vorhandenen Doku-Tiefe orientieren — nicht künstlich aufblähen.
- Wenn ein Projekt bewusst Teile **nicht** dokumentiert (z.B. experimentelle/instabile Features),
  diese Entscheidung respektieren.
