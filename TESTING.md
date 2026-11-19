# Embers of the Vault — v0.9 Playtest Tracker

Statuses: **PASS** = tested and works; **FAIL** = tested and broken; **TEST LATER** = deferred, not a failure. Preserve all TEST LATER entries for subsequent sessions. Do not require every class to reach level 5 in a single session.

Updated 2026-11-18 after user playtest and spell/balance changes. Latest user report: five additional PASS results (Force Barrage/AC rules, descriptions, distinct spell effects, improved difficulty, and finishing-blow continuation). Individual variant tests and all other TEST LATER entries remain deferred. Previously passing checks are noted as **PASS (prior build)** when affected by a subsequent change; retest only where specifically indicated.

| Test | Status | Notes |
| --- | --- | --- |
| Magic d20 attacks vs AC, misses, crits | PASS (prior build) | Retest newly differentiated spells |
| Initiative rerolls every round | PASS | |
| Death mid-round does not skip/repeat turns | PASS | |
| Wizard spells roll vs AC | PASS (prior build) | Force Barrage is now intentionally auto-hit |
| Fighter Power Attack, level 3/5 techniques, action costs | TEST LATER | |
| Rogue Sneak Attack, level 3/5 techniques, action costs | TEST LATER | |
| Cleric Heal and learned offensive spells | TEST LATER | |
| One of two level choices per level | TEST LATER | |
| Level 3/5 choice unlocks only selected ability | TEST LATER | |
| Reload persists abilities, gear, party, progression | TEST LATER | |
| Mira and Lyra magic/healing scale appropriately | TEST LATER | |
| Bram and Vex remain useful | TEST LATER | |
| Complete encounter and advance expedition stage | TEST LATER | |
| Defeat/retry and scouting/ambush | TEST LATER | |
| Force Barrage always hits; other offensive spells roll vs AC | PASS | Confirmed in browser playtest |
| Each learned spell displays a meaningful description | PASS | Confirmed understandable before selection |
| New learned spells have distinct functioning effects | PASS | User confirmed in browser playtest; individual spell variants remain deferred below |
| Frost slows; Flame burns; Storm chains | TEST LATER | Wizard effects |
| Sunfire heals; Judgment weakens attacks; Sacred Flame guards | TEST LATER | Cleric effects |
| Spell effects resolve without freezing combat on a killing blow | PASS | Confirmed combat continues after spell defeats enemy |
| Difficulty after reduced enemy damage and HP scaling | PASS | User reports fairer difficulty without being too easy; broader later-expedition balance remains untested |

**Known code-review follow-ups:** Audit action costs when fewer than two actions remain; audit post-hit effects on finishing blows; confirm spell status effects reset appropriately. These are not reported user failures yet.

When the user submits results, update this file without discarding TEST LATER entries. Merge PR #12 only with explicit user approval.
