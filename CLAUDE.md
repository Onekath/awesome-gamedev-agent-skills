# CLAUDE.md

Remix-Fork von gamedev-skills/awesome-gamedev-agent-skills.
Regeln für Skills: CONTRIBUTING.md und docs/SKILL-FORMAT.md. Vor jedem Commit: `python scripts/validate-skills.py`.

Bevor du einen Skill, den Router, diese CLAUDE.md oder ein anderes Dokument für Agenten anlegst oder änderst, lade zuerst den Skill `mattpocock-skills:writing-for-agents` und arbeite erst danach an der Aufgabe. Das gilt auch für jedes Ticket unter `.scratch/`.

## Agent skills

### Issue tracker

Specs und Tickets liegen als Markdown-Dateien unter `.scratch/<feature>/`. See `docs/agents/issue-tracker.md`.

### Triage labels

Die fünf Standardrollen (needs-triage, needs-info, ready-for-agent, ready-for-human, wontfix) als `Status:`-Zeile. See `docs/agents/triage-labels.md`.

### Domain docs

Single-context: `GLOSSARY.md` und `docs/adr/` im Repo-Root (werden bei Bedarf angelegt). See `docs/agents/domain.md`.
