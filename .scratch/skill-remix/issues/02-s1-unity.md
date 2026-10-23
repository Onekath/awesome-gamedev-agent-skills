# 02: S1 Unity

**What to build:** Die Unity-Skills des Remix sind gegen Unity 6.3 LTS geprüft, korrekt und klar gegen das offizielle Unity-Plugin abgegrenzt: Wo sich Themen überschneiden, verweist der Skill auf den offiziellen Skill oder grenzt sich im Abschnitt „When to use“ ausdrücklich ab. Primärquelle: Unity-Doku 6.3 LTS.

**Blocked by:** 01

**Status:** ready-for-agent

## Schritt 0 (Pflicht, vor allem anderen)

Lade als Allererstes den Skill `mattpocock-skills:writing-for-agents` und lies ihn vollständig, bei Arbeit an Skills auch seine `SKILL-MECHANICS.md`. Erst danach liest du die übrigen Unterlagen und beginnst mit der Aufgabe. Skills, Router und CLAUDE.md sind Dokumente für Agenten; jede Änderung daran folgt diesem Skill.

## Unterlagen

- Spec: `.scratch/skill-remix/spec.md` (Session-Plan, Entscheidungen, Test-Seams)
- Qualitätskriterien und Eval-Anleitung aus Ticket 01
- CONTRIBUTING und der Authoring-Standard des Repos; Versions-Baselines in der Version-Support-Doku
- ADRs und Glossar, falls vorhanden

## Skills in diesem Ticket

- [ ] unity-csharp-scripting (inkl. Projekt-Prüfskript und dessen Tests)
- [ ] unity-input-system
- [ ] unity-physics
- [ ] unity-animation
- [ ] unity-scriptableobjects
- [ ] unity-tilemap-2d
- [ ] unity-navmesh
- [ ] unity-build-pipeline

## Acceptance criteria

- [ ] Schritt 0 erledigt: `writing-for-agents` wurde geladen, bevor irgendetwas bearbeitet wurde
- [ ] Trigger-Evals für jeden Skill dieses Tickets liegen vor (3–5 Positiv-, 1–2 Negativfälle) und wurden **vor** den Änderungen ausgeführt; Ausgangswert ist unter `## Comments` notiert
- [ ] Jeder Skill ist gegen die Qualitätskriterien und die Primärdoku seiner Engine/Disziplin geprüft; Funde stehen unter `## Comments`
- [ ] Funde sind behoben; Code-Beispiele nennen die Version und nutzen keine erfundenen APIs
- [ ] Evals nach den Änderungen: Positivfälle lösen den richtigen Skill aus, Negativfälle nicht; Vergleich zum Ausgangswert ist notiert
- [ ] Routing-Einträge geänderter Skills sind nach dem Verfahren in CONTRIBUTING angepasst
- [ ] Validator und Regressionstests sind grün
- [ ] Änderungen liegen in konventionellen Commits (ein Skill oder eine zusammenhängende Änderung pro Commit)
- [ ] Entscheidungen, die über dieses Ticket hinaus gelten, sind als ADR festgehalten; neue Begriffe im Glossar
- [ ] Für jeden Skill ist notiert, mit welchem Skill des offiziellen Unity-Plugins er sich überschneidet und wie die Abgrenzung aussieht; die Negativ-Evals decken diese Grenzen ab

## Comments
