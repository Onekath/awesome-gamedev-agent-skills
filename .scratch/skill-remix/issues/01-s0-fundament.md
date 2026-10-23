# 01: S0 Fundament: Qualitätskriterien, Evals, Plugin-Test, Unity-Namenskonflikt

**What to build:** Nach diesem Ticket kann jede weitere Session nach denselben Regeln arbeiten und Verbesserungen messen. Es gibt schriftliche Qualitätskriterien für Skills, ein lauffähiges Trigger-Eval-Gerüst mit ersten Fällen für den Router, eine Anleitung, wie der Fork lokal als Plugin getestet und zwischen Original und Remix umgeschaltet wird, und das Unity-Plugin des Remix kollidiert nicht mehr mit dem offiziellen Unity-Plugin.

**Blocked by:** None (can start immediately)

**Status:** ready-for-agent

## Schritt 0 (Pflicht, vor allem anderen)

Lade als Allererstes den Skill `mattpocock-skills:writing-for-agents` und lies ihn vollständig, bei Arbeit an Skills auch seine `SKILL-MECHANICS.md`. Erst danach liest du die übrigen Unterlagen und beginnst mit der Aufgabe. Skills, Router und CLAUDE.md sind Dokumente für Agenten; jede Änderung daran folgt diesem Skill.

## Unterlagen

- Spec: `.scratch/skill-remix/spec.md` (Session-Plan, Entscheidungen, Test-Seams)
- CONTRIBUTING und der Authoring-Standard des Repos; Versions-Baselines in der Version-Support-Doku
- ADRs und Glossar, falls vorhanden

## Acceptance criteria

- [ ] Schritt 0 erledigt: `writing-for-agents` wurde geladen, bevor irgendetwas bearbeitet wurde
- [ ] Qualitätskriterien sind als Dokument im Repo festgehalten; sie bauen auf der PR-Checkliste und dem Authoring-Standard auf und ergänzen Abgrenzung zu Nachbarskills, Verweise statt Doppelungen, Pitfall-Format (Symptom → Ursache → Abhilfe) und Versionsprüfung
- [ ] Ein Trigger-Eval-Gerüst für `claude plugin eval` existiert und läuft; es enthält Fälle für den Router (je Kategorie mindestens ein Positivfall und ein Negativfall)
- [ ] Eine kurze Anleitung beschreibt, wie man Evals für einen Skill ergänzt und ausführt
- [ ] Das Unity-Plugin des Remix hat im Plugin-Manifest einen eigenen Namen; Skill-Namen bleiben unverändert; die Entscheidung ist als ADR festgehalten
- [ ] Eine Anleitung beschreibt, wie der Fork als lokaler Marketplace eingebunden, das passende Original-Plugin deaktiviert und wieder zurückgeschaltet wird; einmal durchgespielt
- [ ] Validator und Regressionstests sind grün
- [ ] Änderungen liegen in konventionellen Commits

## Comments
