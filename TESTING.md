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

## Newly requested checks — 2026-11-18

| Test | Status | Notes |
| --- | --- | --- |
| Wizard melee Strike remains weak while spell attack is near Fighter accuracy | TEST LATER | Level 1 Wizard +6 melee, +9 spell; Fighter +9 melee |
| Cleric and AI caster spell attack scales separately from melee | TEST LATER | |
| Caster level choice labels distinguish spell attack and spell damage | TEST LATER | Verify old saves retain picks |
| Weapon bonuses only affect melee stats, not spell attack | TEST LATER | |
| Damage log shows individual dice and flat modifiers for spells, Strikes, Heal | TEST LATER | e.g. d8(4) + d8(3) + 2 |
| Force Barrage remains unlimited and automatically hits | PASS (prior build) | Retest only if affected |
| Future restricted-rest/limited-spell design | TEST LATER | Not implemented; planning backlog only |

## New martial paths — browser test backlog (2026-11-18)

All checks below default to TEST LATER; previously deferred checks above remain unchanged. Select PASS, FAIL, or TEST LATER for each tested item.

| Test | Status | Notes |
| --- | --- | --- |
| Rogue Sneak Attack triggers with any living ally adjacent to target | TEST LATER | No opposite-side requirement |
| Rogue Precision picks at levels 3/5/7/9 stack d6 correctly | TEST LATER | Mixed-path builds supported |
| Dirty Trick reduces AC by 1 on hit | TEST LATER | |
| Bleeding Cut deals persistent 1d4 at enemy turn start | TEST LATER | |
| Crippling Strike slows next enemy Stride | TEST LATER | |
| Exposing Strike reduces AC by 2 on hit | TEST LATER | |
| Fighter Defensive Stance costs 1 action and grants AC/temporary HP | TEST LATER | |
| Fighter Rallying Strike heals on hit | TEST LATER | |
| Fighter Iron Resolve reduces incoming Strike damage by 2 | TEST LATER | Spell damage reduction is not implemented |
| Fighter Bastion increases maximum HP by 10 | TEST LATER | |
| Fighter Sweeping/Whirlwind/Cleaving/Tempest hit all adjacent enemies | TEST LATER | Separate hit/damage rolls and 2-action cost |
| Prior saves preserve level choices and correctly migrate new effects | TEST LATER | IDs preserved; old selections reinterpreted |
| Full encounters and combat end correctly with multi-target killing blows | TEST LATER | |

## Cleric Restoration / Judgment paths — TEST LATER (2026-11-18)

| Test | Status | Notes |
| --- | --- | --- |
| Level 3 Renewing Prayer heals ally and grants temporary HP | TEST LATER | Two actions, ally target |
| Level 3 Divine Lance damages enemy using spell attack vs AC | TEST LATER | Two actions |
| Level 5 Blessing of Valor buffs melee and spell attack for two rounds | TEST LATER | Two actions, ally target |
| Level 5 Judgment damages and debuffs enemy attack | TEST LATER | Two actions |
| Level 7 Restorative Wave heals every living ally | TEST LATER | Two actions, ally target to activate |
| Level 7 Withering Brand damages and reduces enemy AC | TEST LATER | Two actions |
| Level 9 Sanctuary Aura buffs AC and temp HP of all allies | TEST LATER | Two actions, ally target to activate |
| Level 9 Searing Verdict damages and burns enemy | TEST LATER | Two actions |
| Healing and buffs work without an enemy target and expire correctly | TEST LATER | |
| Hybrid Cleric build mixes Restoration and Judgment choices | TEST LATER | |
| Previously saved Cleric choices and progression behave after update | TEST LATER | IDs retained but options reinterpreted |
| Basic Cleric Heal remains available and unlimited | TEST LATER | |

