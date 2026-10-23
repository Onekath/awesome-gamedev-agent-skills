# 10: S9 Code-first Frameworks (Phase 2)

**What to build:** Die Skills für Phaser, PixiJS, three.js, Bevy, LÖVE und pygame sind gegen ihre Baseline-Versionen geprüft und korrekt. Primärquellen: die jeweilige offizielle Doku und Release Notes.

**Blocked by:** 07

**Status:** ready-for-agent

## Schritt 0 (Pflicht, vor allem anderen)

Lade als Allererstes den Skill `mattpocock-skills:writing-for-agents` und lies ihn vollständig, bei Arbeit an Skills auch seine `SKILL-MECHANICS.md`. Erst danach liest du die übrigen Unterlagen und beginnst mit der Aufgabe. Skills, Router und CLAUDE.md sind Dokumente für Agenten; jede Änderung daran folgt diesem Skill.

## Unterlagen

- Spec: `.scratch/skill-remix/spec.md` (Session-Plan, Entscheidungen, Test-Seams)
- Qualitätskriterien und Eval-Anleitung aus Ticket 01
- CONTRIBUTING und der Authoring-Standard des Repos; Versions-Baselines in der Version-Support-Doku
- ADRs und Glossar, falls vorhanden

## Skills in diesem Ticket

- [ ] phaser-core
- [ ] phaser-arcade-physics
- [ ] pixijs-rendering
- [ ] threejs-scene-setup
- [ ] threejs-materials-lighting
- [ ] threejs-gltf-loading
- [ ] bevy-ecs
- [ ] love2d-core
- [ ] pygame-core

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

## Comments
