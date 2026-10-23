# Spec: Gamedev-Skill-Remix

Status: ready-for-agent

## Problem Statement

Ich nutze die Skill-Suite awesome-gamedev-agent-skills als installiertes Claude-Code-Plugin (Router, Unity, Disciplines, Genres, Workflows). Die Skills sind solide, aber nicht auf meine Arbeit zugeschnitten, und ich kann nicht sicher sagen, wie gut sie sind: ob die Code-Beispiele mit den aktuellen Engine-Versionen stimmen, ob Skills sich überschneiden (z. B. zwei KI-Skills, die beide Behavior Trees lehren) und ob die Beschreibungen den richtigen Skill zuverlässig auslösen. Dazu kommt ein konkreter Konflikt: Das Unity-Plugin dieser Suite heißt genauso wie das offizielle Unity-Plugin, das ich ebenfalls installiert habe. Beide landen im selben Namensraum `unity:`, und ich sehe nicht, welcher Skill wofür zuständig ist.

Ich will die Suite in einem eigenen Fork verbessern, aber in Häppchen, die jeweils in eine Arbeitssession passen, mit so wenigen Sessions wie möglich. Und ich will jede Änderung belegen können, statt nur zu hoffen, dass sie besser ist.

## Solution

Ein Remix der Suite in meinem Fork, abgearbeitet in festen Sessions. Jede Session bündelt Skills, die dieselben Primärquellen brauchen (eine Engine-Doku bzw. eine Disziplin), damit pro Session nur ein Doku-Kontext geladen werden muss.

- **Phase 1** deckt alles ab, was ich installiert habe, in 7 Sessions (S0–S6).
- **Phase 2** (optional) deckt die übrigen Engines ab, in 4 Sessions (S7–S10).

S0 legt das Fundament: Qualitätskriterien, Testaufbau, Lösung des Namenskonflikts. Jede weitere Session prüft ihre Skills gegen diese Kriterien, behebt die Funde und belegt das über zwei Test-Seams: den vorhandenen Validator und neue Trigger-Evals.

### Session-Plan

| Session | Inhalt | Skills |
|---|---|---|
| S0 | Fundament: Qualitätskriterien, Eval-Gerüst, lokales Testen des Forks als Plugin, Lösung des `unity`-Namenskonflikts | – |
| S1 | Unity (inkl. Abgrenzung zum offiziellen Unity-Plugin) | unity-csharp-scripting, unity-input-system, unity-physics, unity-animation, unity-scriptableobjects, unity-tilemap-2d, unity-navmesh, unity-build-pipeline |
| S2 | Disciplines: KI & Systeme | game-ai, ai-behavior-trees-utility-ai, dialogue-systems, save-systems, procedural-gen |
| S3 | Disciplines: Feel & Steuerung | game-feel, camera-systems, physics-tuning, input-systems, game-ui-ux, audio-design |
| S4 | Disciplines: Content & Technik | create-game-assets, shader-programming, level-design, performance-optimization |
| S5 | Genres (nach den Disciplines, weil Genres auf sie verweisen) | platformer, roguelike, rpg, fps-shooter, tower-defense, card-game, visual-novel, survival-crafting, puzzle |
| S6 | Workflows, Router, Abschluss (Katalog, Manifest, Gesamtlauf) | game-jam, prototype-fast, itch-publish, steam-publish, router |
| S7 (Phase 2) | Godot Core | godot-gdscript, godot-csharp, godot-nodes-scenes, godot-signals-groups, godot-resources, godot-gdscript-headless-testing, godot-export, godot-multiplayer |
| S8 (Phase 2) | Godot Gameplay | godot-2d-movement, godot-3d-essentials, godot-physics, godot-tilemap, godot-animation, godot-audio, godot-shaders, godot-ui-control |
| S9 (Phase 2) | Code-first Frameworks | phaser-core, phaser-arcade-physics, pixijs-rendering, threejs-scene-setup, threejs-materials-lighting, threejs-gltf-loading, bevy-ecs, love2d-core, pygame-core |
| S10 (Phase 2) | Unreal & Roblox | unreal-blueprints, unreal-cpp-gameplay, unreal-enhanced-input, unreal-behavior-trees, unreal-niagara, unreal-packaging, roblox-luau, roblox-characters, roblox-datastores, roblox-networking, roblox-physics, roblox-studio-workflow, roblox-ui |

Faustregel für den Zuschnitt: höchstens ~10 Skills bzw. ~3.000 Zeilen Skill-Material pro Session, und nur eine Engine-Doku pro Session.

## User Stories

1. Als Remix-Autor will ich die Suite in Sessions mit festem Umfang abarbeiten, damit ich jede Session in einem Rutsch abschließen kann.
2. Als Remix-Autor will ich so wenige Sessions wie möglich, damit der Remix nicht ausufert.
3. Als Remix-Autor will ich, dass eine Session nur Skills mit denselben Primärquellen enthält, damit pro Session nur eine Doku geladen und geprüft werden muss.
4. Als Remix-Autor will ich, dass die Kategorien, die ich installiert habe, zuerst drankommen, damit sich der Remix sofort in meiner Arbeit bemerkbar macht.
5. Als Remix-Autor will ich die übrigen Engines als optionale Phase 2, damit ich später entscheiden kann, ob sie den Aufwand wert sind.
6. Als Remix-Autor will ich schriftliche Qualitätskriterien, bevor die erste Skill-Session startet, damit alle Sessions gleich streng prüfen.
7. Als Remix-Autor will ich, dass die Qualitätskriterien auf der vorhandenen PR-Checkliste und dem Authoring-Standard des Repos aufbauen, damit der Remix kompatibel zum Original bleibt.
8. Als Remix-Autor will ich, dass jede Session mit einem grünen Validator endet, damit kein Skill und keine Verdrahtung kaputtgeht.
9. Als Remix-Autor will ich pro Skill Trigger-Evals, damit ich belegen kann, dass eine Beschreibung den richtigen Skill auslöst.
10. Als Remix-Autor will ich die Trigger-Evals vor einer Änderung als Ausgangswert laufen lassen, damit ich eine Verbesserung messen kann statt sie zu behaupten.
11. Als Remix-Autor will ich auch Negativfälle in den Evals (Prompts, die einen Skill gerade nicht auslösen sollen), damit benachbarte Skills sich nicht gegenseitig die Anfragen wegnehmen.
12. Als Remix-Autor will ich meinen Fork lokal als Plugin testen können, damit ich die Remix-Version statt der installierten Original-Version ausprobiere.
13. Als Remix-Autor will ich eine klare Anleitung, wie ich zwischen Original-Plugin und Remix umschalte, damit ich nicht aus Versehen beide gleichzeitig aktiv habe.
14. Als Unity-Entwickler will ich, dass die Unity-Skills des Remix nicht mehr mit dem offiziellen Unity-Plugin um denselben Namensraum konkurrieren, damit ich sehe, welcher Skill wofür zuständig ist.
15. Als Unity-Entwickler will ich, dass sich die Unity-Skills des Remix inhaltlich vom offiziellen Unity-Plugin abgrenzen und bei Überschneidung darauf verweisen, damit ich keine doppelten oder widersprüchlichen Anleitungen bekomme.
16. Als Unity-Entwickler will ich, dass alle Unity-Beispiele gegen Unity 6.3 LTS geprüft sind, damit ich keine veralteten oder erfundenen APIs übernehme.
17. Als Spieleentwickler will ich, dass jedes Code-Beispiel die Engine-Version nennt und gegen die Primärdoku geprüft ist, damit ich ihm vertrauen kann.
18. Als Spieleentwickler will ich, dass Skills mit überlappenden Themen (z. B. game-ai und ai-behavior-trees-utility-ai) klar abgegrenzt sind, damit der Router den passenden auswählt.
19. Als Spieleentwickler will ich, dass jeder Skill im Abschnitt „When to use“ sagt, was er nicht abdeckt und wohin stattdessen, damit ich nicht im falschen Skill lande.
20. Als Spieleentwickler will ich, dass engine-übergreifende Disciplines-Skills für jede genannte Engine korrekte Beispiele oder korrekte Verweise auf den Engine-Skill enthalten, damit die Übertragung auf meine Engine stimmt.
21. Als Spieleentwickler will ich, dass die Genre-Skills auf die Disciplines-Skills verweisen statt Grundlagen neu zu erklären, damit es keine widersprüchlichen Doppelungen gibt.
22. Als Spieleentwickler will ich, dass die Pitfalls jedes Skills nach dem Muster „Symptom → Ursache → Abhilfe“ aufgebaut sind, damit ich Fehler schnell zuordnen kann.
23. Als Spieleentwickler will ich, dass Skills unter der vorgegebenen Längengrenze bleiben und Vertiefung in Referenzdateien liegt, damit beim Auslösen nicht unnötig Kontext verbraucht wird.
24. Als Spieleentwickler will ich, dass mitgelieferte Skripte (z. B. Projekt-Checks für Unity, Godot, Steam) laufen, eine Hilfe-Ausgabe haben und sicher fehlschlagen, damit ich sie gefahrlos nutzen kann.
25. Als Spieleentwickler will ich, dass der Router nach dem Remix alle geänderten Skills findet und richtig zuordnet, damit die Suite als Ganzes funktioniert.
26. Als Spieleentwickler will ich, dass die Workflow-Skills für Steam und itch.io dem aktuellen Stand der Plattformen entsprechen, damit Veröffentlichungen nicht an veralteten Schritten scheitern.
27. Als Remix-Autor will ich pro Session ein eigenes Ticket mit Unterpunkten je Skill, damit ich den Fortschritt innerhalb der Session sehe.
28. Als Remix-Autor will ich, dass jede Session ihre Funde und Entscheidungen festhält, damit spätere Sessions darauf aufbauen können (z. B. S5 auf den Abgrenzungen aus S2–S4).
29. Als Remix-Autor will ich, dass die Reihenfolge der Sessions Abhängigkeiten berücksichtigt (S0 zuerst, Genres nach Disciplines, Router zuletzt), damit keine Session auf Ergebnisse wartet, die es noch nicht gibt.
30. Als Remix-Autor will ich, dass Sessions ohne gegenseitige Abhängigkeit (S1–S4) in beliebiger Reihenfolge oder parallel laufen können, damit ich flexibel bleibe.
31. Als Remix-Autor will ich, dass Änderungen pro Session in eigenen, konventionell benannten Commits landen, damit ich sie einzeln nachvollziehen und gegebenenfalls zurücknehmen kann.
32. Als Remix-Autor will ich neue Upstream-Versionen weiterhin einmergen können, damit mein Remix nicht vom Original abgehängt wird.
33. Als Remix-Autor will ich, dass Katalog-Zahlen, README und Plugin-Manifest am Ende zum Stand des Remix passen, damit der Validator und die Installation stimmen.
34. Als Remix-Autor will ich, dass alle Texte original bleiben und aus Primärdoku geschrieben sind, damit die Lizenz- und Originalitätsregeln des Repos eingehalten werden.
35. Als Remix-Autor will ich, dass Phase-2-Sessions denselben Ablauf und dieselben Kriterien nutzen wie Phase 1, damit ich sie später ohne neue Planung starten kann.

## Implementation Decisions

- **Zuschnitt der Sessions** wie im Session-Plan oben. Kriterium: gemeinsame Primärquelle, höchstens ~10 Skills bzw. ~3.000 Zeilen pro Session.
- **Reihenfolge:** S0 vor allen anderen. S1–S4 sind voneinander unabhängig. S5 nach S2–S4. S6 nach allen Sessions, die Skills verändern, die der Router kennt. Phase 2 (S7–S10) optional und nach S6; wenn Phase 2 läuft, prüft deren letzte Session den Router erneut.
- **Ablauf pro Skill** (in jeder Session gleich): Trigger-Evals als Ausgangswert → Skill gegen die Qualitätskriterien und die Primärdoku der Session prüfen → Funde beheben → Evals und Validator erneut → Ergebnis im Ticket festhalten.
- **Qualitätskriterien** entstehen in S0 und bauen auf der PR-Checkliste in CONTRIBUTING und dem Authoring-Standard (Frontmatter, Body-Aufbau, Version-Pinning, Längengrenze, Originalität) auf. Ergänzt werden: Abgrenzung zu Nachbarskills, Verweise statt Doppelungen, Pitfall-Format, Prüfung jeder Version gegen den Baseline-Stand.
- **Namenskonflikt `unity`:** Das Unity-Plugin des Remix bekommt im Plugin-Manifest einen eigenen Namen, damit es nicht mit dem offiziellen Unity-Plugin kollidiert. Der genaue Name wird in S0 festgelegt und als ADR festgehalten. Skill-Namen selbst bleiben unverändert, damit der Router und die Upstream-Merges funktionieren.
- **Testen des Forks als Plugin:** Der Fork wird lokal als Marketplace eingebunden; das entsprechende Original-Plugin wird dafür deaktiviert. S0 dokumentiert das Umschalten.
- **Router-Änderungen** nur über das bestehende Verfahren aus CONTRIBUTING (Routing-Tabelle, Detection, Composition, Distribution). Sessions S1–S5 passen nur Routing-Einträge geänderter Skills an; die Gesamtprüfung des Routers gehört zu S6.
- **Entscheidungen**, die über eine Session hinaus gelten (Namensgebung, Abgrenzung zwischen Skills, Kriterien), werden als ADR festgehalten; neue Fachbegriffe ins Glossar.
- **Tickets:** ein Ticket pro Session, nummeriert in Session-Reihenfolge, mit je einem Unterpunkt pro Skill.
- **Commits:** konventionelle Commits pro Skill oder zusammenhängender Änderung, wie im Repo üblich (`fix(unity): …`, `refactor(disciplines): …`).

## Testing Decisions

- **Gute Tests prüfen nur äußeres Verhalten:** Wird für einen Prompt der richtige Skill ausgelöst? Sind Repository-Struktur und Verdrahtung gültig? Nicht geprüft wird der Wortlaut eines Skills.
- **Seam 1 (vorhanden): der Repository-Validator** samt seiner Regressionstests. Er prüft Frontmatter, Links, Referenzen, JSON-Assets, Router-Abdeckung, Katalog-Zahlen und Plugin-Manifeste. Pflicht am Ende jedes Tickets und Teil der CI. Stand bei Spec-Erstellung: alle Prüfungen grün.
- **Seam 2 (neu, der einzige neue Seam): Trigger-Evals** über das Plugin-Eval-Werkzeug von Claude Code. Pro Skill 3–5 Prompts, die ihn auslösen sollen, und 1–2 Negativfälle aus benachbarten Skills. S0 baut das Gerüst und die Fälle für den Router; jede weitere Session ergänzt die Fälle ihrer Skills. Das Werkzeug liefert einen Vergleich gegen einen Lauf ohne Plugin mit.
- **Korrektheit der Code-Beispiele** wird gegen die Primärdoku der jeweiligen Engine geprüft (Review, kein automatischer Test). Wo es Projekt-Prüfskripte gibt (Unity, Godot, Steam, Asset-Tools), werden diese mit ihren vorhandenen Tests ausgeführt.
- **Vorbild im Repo:** die Validator-Tests und die Tests für die Projekt-Prüfskripte (Unity, Godot, Steam, Asset-Tools).

## Out of Scope

- Neue Skills oder neue Kategorien. Der Remix verbessert die vorhandenen 74 Skills und den Router.
- Neue Engines oder ein Wechsel der Baseline-Versionen. Gilt der Baseline-Stand nicht mehr, wird das festgehalten, die Migration aber nicht in diesem Remix gemacht.
- Pull Requests an das Original-Repo. Ob einzelne Verbesserungen zurückfließen, wird später entschieden.
- Umbau der Doku-Website und ihrer Skripte.
- Phase 2 ist Teil dieser Spec, aber optional; ohne sie gilt der Remix nach S6 als abgeschlossen.

## Further Notes

- Ausgangsstand: Fork auf Upstream-Commit 38a4c25, identisch zur installierten Plugin-Version.
- Upstream bleibt als zweites Remote eingetragen. Merges von Upstream finden zwischen Sessions statt, nicht mittendrin.
- Mögliche Funde für eigene Folgetickets: Überschneidungen zwischen Disciplines und Genres, die erst in S5 sichtbar werden; veraltete Plattformschritte bei Steam und itch.io.
