# Embers of the Vault — v0.9 Active Playtest Checklist

Updated 2026-11-19. This is the **active, untested backlog only**, verified against the current v0.9 game.js. Rows now include user-confirmed **PASS** results alongside outstanding **TEST LATER** checks; no FAIL results reported. Completed PASS checks and obsolete tests for replaced abilities have been removed. Do not re-add passed checks without a relevant code change. Test classes and levels over multiple sessions; there is no requirement to reach level 9 in one playtest.

**Status:** 14 checks confirmed PASS on 2026-11-18; PR #12 remains open and unmerged. Update individual rows to PASS or FAIL when the user reports results; keep untested rows deferred.

## General progression, persistence and expedition

| Test | Status | Notes |
| --- | --- | --- |
| Only one of two choices can be selected per level, and only the chosen ability unlocks | PASS |Check levels 3/5/7/9; User confirmed 2026-11-18 |
| Reload retains level picks, unlocked abilities, equipment, party and expedition progress | PASS |Include reloading a battle-ready save; User confirmed 2026-11-18 |
| Existing saves still load; old level-choice IDs map to the newly replaced abilities without breaking play | PASS |Prior ability meanings changed; communicate this clearly; User confirmed 2026-11-18 |
| Complete an encounter and advance to the next expedition stage | PASS |; User confirmed 2026-11-18 |
| Defeat, retry, scouting and ambush flow | PASS |; User confirmed 2026-11-18 |
| Later-expedition enemy balance remains fair | PASS |Early difficulty was previously PASS; only later levels untested; User confirmed 2026-11-18 |
| Two-action skills/spells cannot activate with fewer than two actions | PASS |Check targeting and resource use; User confirmed 2026-11-18 |
| Offensive spell or multi-target finishing blows resolve encounter without lost turns or frozen UI | PASS |Previous basic finishing-blow test PASS; check new mechanics only; User confirmed 2026-11-18 |
| Debuffs, buffs, temporary HP and damage-over-time expire/reset at the intended time | TEST LATER | Across rounds and encounters |
| Damage log displays individual dice and modifiers for melee, offensive spells and Heal | TEST LATER | Verify critical-hit math |
| Wizard melee Strike +6 vs spell attack +9 and Fighter melee +9 at level 1 | PASS |Differentiate spell and weapon attacks; User confirmed 2026-11-18 |
| Cleric and AI caster spell attack scales independently of melee | TEST LATER | |
| Caster level choices clearly distinguish spell attack from spell damage | PASS |; User confirmed 2026-11-18 |
| Weapon upgrades improve melee only, not spell attacks | TEST LATER | |
| Mira/Lyra magic and healing scale with level; Bram/Vex remain useful | TEST LATER | Compare higher-level encounters |

## Fighter — durability and cleaving

| Test | Status | Notes |
| --- | --- | --- |
| Power Attack deals its extra d8 and consumes two actions | TEST LATER | Base Fighter action still present |
| Level 3 Defensive Stance costs one action and grants +2 AC plus 3 temporary HP | TEST LATER | Check when bonuses expire |
| Level 3 Sweeping Strike hits all adjacent enemies, each with its own attack roll | TEST LATER | Two actions |
| Level 5 Rallying Strike heals 5 + level HP on hit | TEST LATER | |
| Level 5 Whirlwind Strike hits all adjacent enemies for +1d6 per successful hit | TEST LATER | |
| Level 7 Iron Resolve prevents 2 incoming melee Strike damage | TEST LATER | Not spell damage in current implementation |
| Level 7 Cleaving Arc hits all adjacent enemies for +1d8 per hit | TEST LATER | |
| Level 9 Bastion adds 10 maximum HP | TEST LATER | |
| Level 9 Tempest Sweep hits all adjacent enemies for +2d6 per hit | TEST LATER | |
| Fighter can mix durability and cleaving picks at different levels | TEST LATER | |

## Rogue — precision and sabotage

| Test | Status | Notes |
| --- | --- | --- |
| Sneak Attack activates when any living ally is adjacent to the target | TEST LATER | Opposite-side flanking no longer required |
| Precision picks at levels 3/5/7/9 stack +1d6 Sneak Attack each | TEST LATER | Check dice log and critical hits |
| Level 3 Dirty Trick reduces enemy AC by 1 on hit | TEST LATER | |
| Level 5 Bleeding Cut deals persistent 1d4 at start of enemy turns | TEST LATER | Current bleed has no recovery check |
| Level 7 Crippling Strike limits enemy's next Stride to 2 tiles | TEST LATER | |
| Level 9 Exposing Strike reduces enemy AC by 2 on hit | TEST LATER | |
| Rogue can mix Sneak Attack upgrades and sabotage techniques | TEST LATER | |

## Cleric — restoration and judgment

| Test | Status | Notes |
| --- | --- | --- |
| Basic Heal remains unlimited and can target an ally | TEST LATER | Two actions |
| Level 3 Renewing Prayer heals 2d8 + level and grants 3 temporary HP | TEST LATER | Ally target |
| Level 3 Divine Lance deals 2d8 + level vs enemy AC | TEST LATER | |
| Level 5 Blessing of Valor grants +2 melee and spell attack for two rounds | TEST LATER | Check duration |
| Level 5 Judgment deals 2d8 + level and reduces enemy attack by 1 on hit | TEST LATER | |
| Level 7 Restorative Wave heals all living allies 1d8 + level | TEST LATER | |
| Level 7 Withering Brand deals 2d6 + level and reduces enemy AC by 2 on hit | TEST LATER | |
| Level 9 Sanctuary Aura grants all allies 5 temporary HP and +2 AC for two rounds | TEST LATER | |
| Level 9 Searing Verdict deals 2d8 + level and burns on hit | TEST LATER | |
| Support spells work without an enemy target and cannot target enemies | TEST LATER | |
| Cleric can mix Restoration and Judgment choices | TEST LATER | |

## Wizard — elemental devastation and arcane affliction

| Test | Status | Notes |
| --- | --- | --- |
| Level 3 Flame Burst hits enemies within radius 1 with separate attack/damage rolls | PASS |; User confirmed 2026-11-18 |
| Level 3 Frost Lance deals damage and slows next Stride on hit | TEST LATER | |
| Level 5 Thunderstorm hits enemies within radius 2 | PASS |; User confirmed 2026-11-18 |
| Level 5 Flame Lance deals damage and burns on hit | TEST LATER | |
| Level 7 Meteor Shower hits enemies within radius 2 for 3d6 + level | TEST LATER | |
| Level 7 Crippling Ray deals 3d8 + level and reduces enemy attack by 2 on hit | TEST LATER | |
| Level 9 Arcane Cataclysm hits enemies within radius 3 for 4d6 + level | TEST LATER | |
| Level 9 Doom Bolt deals 4d8 + level and reduces enemy AC by 2 on hit | TEST LATER | |
| AoE can target an empty tile in range, excludes allies, and resolves last-enemy kills | PASS |; User confirmed 2026-11-18 |
| Wizard can mix AoE and single-target spell choices | PASS |; User confirmed 2026-11-18 |

## Code-review concerns to verify during tests

These are **not confirmed user-reported failures**.

| Test | Status | Notes |
| --- | --- | --- |
| Post-hit debuff/secondary effects resolve correctly when the primary hit ends the encounter | TEST LATER | Current code may return early after checkEnd() |
| Round-based spell buffs actually decrement and expire at round transitions | TEST LATER | Review endTurn() and advanceDead() behavior |
| Area spell attack penalties and damage rolls behave consistently across multiple targets | TEST LATER | Check each target gets independent attack and dice |

**Previously passed and removed from active backlog:** initiative rerolls each round; dead units do not skip/repeat turns; core d20 magic-vs-AC mechanics; Force Barrage automatic hit; understandable learned-spell descriptions; original distinct spell effects; original spell finishing-blow continuation; and early difficulty adjustment. **Obsolete and removed:** old Fighter Shield Bash/Sundering Blow, Rogue Twin Cut/Shadow Strike, Wizard Arcane Lance/Storm Lance, Cleric Sunfire/Sacred Flame, and the older level 3/5 generic skill/spell tests. **Not in the test backlog:** the future restricted-rest/limited-spell idea, because it has not been implemented.


## New v0.9 changes — TEST LATER (2026-11-19)

| Test | Status | Notes |
| --- | --- | --- |
| Main page and preview header display Levels 1–10 without prematurely merging v0.9 gameplay | TEST LATER | Main index.html header only |
| Level-up spell cards show Area Spell / Debuff Spell and path names, never +0 | TEST LATER | Verify all four classes' ability cards |
| Fire Burst remains radius 1; Flame Burst radius 2, Thunderstorm 3, Meteor Shower 4, Cataclysm 5 | TEST LATER | Check clear progression |
| AoE circular area includes diagonal targets within Euclidean radius, excludes targets outside circle | TEST LATER | Test (1,1), (2,2), (3,3) offsets where appropriate |
| Existing generated expeditions and new expeditions grant increased treasure silver correctly | TEST LATER | No double award on replay |
| Searching caches grants 16–28 silver and optional fire flask | TEST LATER | Ambush chance unchanged |
| Existing legacy single save migrates to Slot 1 without deleting original | TEST LATER | Back up browser storage before testing |
| Three save slots keep independent classes, party, level, inventory and progress | TEST LATER | Switching slots, reload browser, continue |
| Starting a new campaign in an occupied slot requires confirmation and cancel preserves save | TEST LATER | |
| Sound effects default off; Sound toggle plays short sounds on melee and spell attacks | TEST LATER | User gesture required; no music yet |

**Regression note:** The user's earlier PASS for Flame Burst radius 1 and Thunderstorm radius 2 applied to the previous implementation. The newly expanded radii and circular targeting must be tested, but unrelated prior PASS results remain valid.
