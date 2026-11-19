# Embers of the Vault — Browser Tactical RPG

A dependency-free, browser-based tactical RPG inspired by Pathfinder Second Edition. **v0.8 is merged into `main`; v0.9 is in development in PR #12.** This is a simplified game, not a complete implementation of Pathfinder 2e.

**Play:** https://giswindsor.github.io/embers-of-the-vault/  
**Development preview:** https://giswindsor.github.io/embers-of-the-vault/preview/  
**v0.9 pull request:** https://github.com/GISWindsor/embers-of-the-vault/pull/12

## Getting started

Play in a modern desktop or mobile browser, or open `index.html` locally. No dependencies or build step are needed. Choose Kael's class (Fighter, Rogue, Cleric, or Wizard), choose two AI companions, and begin an expedition. Progress is saved to browser localStorage, so changing browsers/devices or clearing site data may remove it.

## Gameplay and controls

- **Three-action turns:** Stride, Strike, raise a shield, drink a potion, use a class ability, or end your turn. Some abilities and consumables cost two actions.
- **Tactical combat:** Isometric grid, obstacles, flanking, multiple attack penalties (0/−5/−10), d20 attack rolls, degrees of success, and critical hits.
- **Camp:** Rest, equip gear, select companions, inspect stats, make level-up choices, and choose the next destination.
- **Exploration:** Route selection, scouting with a limited budget, persistent intelligence, and supply searches that can trigger an ambush.
- **Resources:** Earn XP, silver, and loot from encounters; purchase or use consumables and manage equipment.
- **Expeditions:** Procedurally assembled five-stage expeditions with alternate routes, enemy groups, terrain, and rewards. Completing an expedition lets the party continue to another with its progression intact.
- **AI companions:** Select two from Mira (Cleric), Vex (Rogue), Bram (Fighter), and Lyra (Wizard).

## Released features

### v0.2–v0.6: Foundations

Class selection, a three-action combat system, persistent campaign saves, XP and gear, a four-companion roster, and branching routes through the original Ember Road campaign. These early version descriptions are historical: the game has evolved beyond the original fixed encounters.

### v0.7: Camp and usability improvements

Updated camp and game interface, with mobile usability improvements including scrolling fixes.

### v0.8: Procedural expeditions and progression (merged)

- Five-stage procedural expeditions with multiple route choices.
- New expeditions after completion while retaining the party, class, level, XP, inventory, silver, and equipment.
- Enemy and companion scaling as the party levels.
- Two scouting opportunities per campaign, with discovered intelligence retained.
- Supply-search ambush chance, with rewards and no advancement of the current expedition stage.
- Compatibility handling for older campaign saves.

## v0.9 — Development preview (not yet merged)

The following features are **on the v0.9 feature branch and preview**, not yet part of the released `main` game:

- **Level-by-level choices:** Two distinct, class-specific options at each level (1–10). Choose one; the choice is permanent and persists in saves. Choices can improve HP, AC, attack, or damage.
- **Ability unlocks:** At levels 3 and 5, Wizards and Clerics choose between two new spells; Fighters and Rogues choose between two combat techniques. These choices replace the ordinary stat options at those levels.
- **Companion stat sheets:** The two selected companions appear in a stat row above the four companion-selection choices. Sheets display HP, AC, attack, damage, initiative modifier, and level.
- **Initiative each round:** All living combatants roll d20 plus their initiative modifier at the beginning of combat and at the start of each new round; turn order can change.
- **Damage display:** Character sheets show a normal Strike damage range instead of an unexplained base-damage value.
- **Spell attacks:** Offensive magic attacks roll d20 plus an attack modifier against the target's AC, with misses, hits, and critical hits shown in the log. Healing does not require an attack roll.
- **Scaling magic:** AI Cleric healing and AI Wizard damage improve with party level; enemy caster attacks use AC and scale with enemy level.
- **Martial techniques:** Fighters can unlock Shield Bash, Sweeping Strike, Sundering Blow, or Rallying Strike; Rogues can unlock Dirty Trick, Twin Cut, Shadow Strike, or Bleeding Cut, depending on their level 3 and 5 selections.

**Balance status:** v0.9 mechanics are experimental and still require user browser testing and balancing before merge. The magic rules are deliberately simplified; for example, the game currently uses attack-vs-AC for offensive magic rather than Pathfinder 2e's full distinction between spell attacks and saving-throw spells.

## Rules and limitations

This is a PF2e-inspired prototype, not an official Pathfinder 2e rules implementation. Movement uses four-square Strides and simplified adjacency; combat omits many conditions, reactions, and character-building rules. Spell effects, progression bonuses, enemy AI, and loot are simplified for browser play. Some actions (such as consumable fire effects) also use custom rules.

## Project files

- `index.html` — self-contained browser entry point with inline game logic and styles, used by the hosted game.
- `game.js` — source game logic and combat implementation.
- `style.css` — source visual styling.
- `preview/index.html` — preview published through GitHub Pages.

When changing gameplay or styles, keep the standalone `index.html` synchronized with `game.js` and `style.css`. Update this README whenever player-facing mechanics or release status change.

## Development workflow

Features are developed on branches, previewed in the browser, and reviewed in pull requests. **Do not merge an in-development PR into `main` until the user approves the browser playtest and explicitly authorizes the merge.** The `preview/` page may show features that are not yet in the released game.

## v0.9 spell differentiation and balance (preview)

Force Barrage is an automatic-hit spell again; other offensive spells roll against AC. Level 3 and 5 spells now have descriptions and different damage/effects: cold slows movement, fire burns, lightning chains, divine magic can heal, debuff attacks, or protect the caster. Enemy Strike damage is reduced by 1, with slightly lower high-level HP scaling. These are experimental and need browser playtests.

## Testing policy

Record each check as **PASS**, **FAIL**, or **TEST LATER**. TEST LATER means untested and remains on the future-test backlog; it is not a failure and must not be silently counted as a pass. Avoid requiring every class to reach high levels in one play session. See `TESTING.md` on the development branch for the persistent checklist.

## v0.9: Separate spell and melee accuracy, dice transparency

- Wizard melee Strike remains +6 at level 1, while spell attack is +9 (matching Fighter's +9 melee accuracy); Cleric melee +7 and spell attack +8. Lyra's and Mira's spell accuracy use separate level-scaled values as well.
- Melee Strike attack/damage and spell attack/damage are separate stats. Equipped weapons improve melee only. Caster level choices that previously gave generic attack or damage now explicitly increase spell attack or spell damage; martial choices remain melee bonuses. Existing save pick IDs are preserved.
- Character sheets distinguish melee Strike bonus/damage from spell attack bonus and spell damage bonus. Spell attack breakdown shows class, level and spell-feat contributions.
- Combat logs show rolled damage dice and modifiers, e.g. `d8(4) + d8(3) + 2 = 9`, in addition to d20 attack checks. Force Barrage remains the unlimited automatic-hit spell. Healing dice are shown too.
- **Future direction (not implemented):** Make resting and healing between encounters substantially scarcer. Consider limited-use stronger spells, but retain at least one unlimited-use offensive spell. If limited spells are introduced, they must deal some damage even on a failed attack, with additional damage on a successful attack. Design and balance this later, not in this patch.

## v0.9 martial paths (preview; not merged)

Rogue: Sneak Attack triggers on a successful melee Strike when any living ally is adjacent to the target (no opposite-side requirement). At levels 3/5/7/9 choose either stacking +1d6 Sneak Attack or an active debuff: Dirty Trick (−1 AC), Bleeding Cut (persistent 1d4 bleed at enemy turn start), Crippling Strike (next Stride limited to 2 tiles), Exposing Strike (−2 AC). Precision bonuses accumulate and hybrid choices are allowed. Bleeding is persistent for the encounter; no recovery check yet.

Fighter: at levels 3/5/7/9 choose durability or multi-target damage. Defensive Stance (1 action, +2 AC and 3 temporary HP), Rallying Strike (2-action hit heals 5+level), Iron Resolve (passive −2 incoming melee Strike damage), Bastion (+10 max HP); or Sweeping Strike (all adjacent enemies), Whirlwind Strike (+1d6 each), Cleaving Arc (+1d8 each), Tempest Sweep (+2d6 each). Multi-target abilities cost 2 actions and roll separately for each enemy. These mechanics are experimental and may need balance tuning.

Existing saved level-pick IDs remain intact, but prior martial choices at levels 3, 5, 7 and 9 now resolve to the new paths; previously saved builds may therefore have different effects. Retest save migration.

## v0.9 Cleric paths (preview, not merged)

Cleric chooses independently at levels 3/5/7/9 between **Restoration** and **Judgment**. Level 3: Renewing Prayer (2d8+level ally heal and 3 temporary HP) or Divine Lance (2d8+level spell attack). Level 5: Blessing of Valor (+2 melee/spell accuracy for 2 rounds) or Judgment (2d8+level and -1 enemy attack on hit). Level 7: Restorative Wave (1d8+level heal to each living ally) or Withering Brand (2d6+level and -2 enemy AC on hit). Level 9: Sanctuary Aura (5 temporary HP and +2 AC for 2 rounds to each ally) or Searing Verdict (2d8+level and burning 1d4 on hit). Support spells target allies; offensive spells target enemies. Each costs 2 actions. Existing basic Heal remains available and unlimited. Choices may be mixed across levels.

**Save migration note:** Cleric level 3/5 choices retain IDs a/b, but the ability represented by a prior saved choice may change. Existing level 7/9 choices also change. Check saves before merging. Temporary HP and buffs are combat-only. These paths require browser playtests.

## v0.9 Wizard specializations (preview, not merged)

At levels 3/5/7/9 the Wizard may choose **Elemental Devastation** (large AoE) or **Arcane Affliction** (single-target damage/debuff). Level 3: Flame Burst (radius 1, 2d6+level fire) / Frost Lance (2d6+level, slows). Level 5: Thunderstorm (radius 2, 2d6+level lightning) / Flame Lance (2d6+level, burns). Level 7: Meteor Shower (radius 2, 3d6+level fire) / Crippling Ray (3d8+level, -2 enemy attack on hit). Level 9: Arcane Cataclysm (radius 3, 4d6+level arcane) / Doom Bolt (4d8+level, -2 enemy AC on hit). Each costs two actions and has casting range 6. AoE spells choose a tile and roll separately against each enemy within a Euclidean/circular radius (including diagonals), never hitting allies. Fire Burst remains the basic radius-1 spell; learned Flame Burst, Thunderstorm, Meteor Shower and Arcane Cataclysm use radius 2/3/4/5 respectively. Choices may be mixed across levels. Force Barrage stays unlimited and automatically hits.

**Save compatibility:** Wizard level picks retain IDs a/b, but older saved choices at levels 3/5/7/9 now map to these new effects. Browser testing is required before merging.

## v0.9 interface, loot, sound and save slots

- Header now advertises levels **1–10**. The main landing page header was corrected without merging v0.9 gameplay into main.
- Level-choice spell rows now display meaningful categories/path names rather than “+0 area spell” or “+0 new spell”.
- Area spells use Euclidean distance (circular tile selection, including diagonal tiles within radius). Basic Fire Burst is radius 1; learned Flame Burst/Thunderstorm/Meteor Shower/Arcane Cataclysm are radii 2/3/4/5. Casting range remains 6 tiles. Damage dice remain unchanged.
- Generated expedition stage silver is increased from 18 + 10 × stage to 30 + 16 × stage, plus an additional post-battle cache of 10–20 + 5 × stage silver. Search caches increase from 8–14 to 16–28 silver. Older saved expeditions retain their generated base silver but gain the post-battle cache.
- Three browser-local save slots. Existing legacy single save is copied into slot 1 (original legacy key is retained); choosing a different slot allows a separate campaign. Starting over in an occupied slot requires confirmation. Saving and continuing use the selected slot. Saves are local to this browser/device, not cloud-synced.
- Optional **Sound: Off/On** toggle for short synthesized melee and spell sound effects. Sound is off by default; no music is included yet. Browser Web Audio support required.
- New functionality is syntax-checked but needs manual browser verification. PR #12 remains open and unmerged.

## Encounter-ending music (v0.9 preview)

With **Sound: On**, victory plays a short, original ascending celebratory melody and defeat plays a short, original descending somber melody. Both are synthesized in the browser using Web Audio (no copyrighted music or external audio files). **Sound: Off** is the default; toggling sound off stops a playing ending tune. Encounter-ending music is triggered once at the actual win/loss transition and continues briefly over the camp screen. Starting another encounter stops the previous tune. Music availability depends on browser audio permissions and user interaction.

## v0.9 full-party manual combat control (preview, not merged)

Every allied party member, including the hero and both chosen companions, now has a manual three-action turn in rerolled initiative order. The current acting character is highlighted on the board and shown in the action header; the actions adapt to the actor's class: Fighter Power Attack, Rogue passive Sneak Attack, Cleric Heal, and Wizard Force Barrage/Fire Burst, alongside Stride, Strike, shield, potions and fire flasks. Enemies remain AI-controlled. The hero's selected level-path techniques/spells stay exclusive to the hero; companions currently use their baseline class abilities and existing level-scaled statistics, **not independent level-up choices or inventories**. Consumables remain party-shared. Party defeat now requires all allied characters to fall instead of immediately losing when Kael falls. This is a first full-party-control implementation; manual browser testing is required before merge.

## Expedition item treasure drops (v0.9 preview)

Fixed missing item rewards in procedurally generated expeditions. Each victorious normal expedition encounter now has a 45% chance to award one previously unowned piece of equipment from the existing equipment pool: Reinforced Armor, Emberforged Weapon, Warded Cloak, Cinder Talisman. The final stage of each expedition guarantees an unowned equipment item if any remain. Ambushes still grant silver/XP, not equipment. Duplicates are not awarded; after all four items are collected, there are no further equipment drops from this pool. Item rewards appear in victory text, inventory, and camp equip options; existing saved expeditions are compatible and future wins use the new rules. Past wins are not retroactively awarded items. This is a first loot fix; item diversity and level-scaled loot are future design work.

## Party-control direction restored (2026-11-18)

The intended design is a simulation of adventuring with other players: **only Kael is directly controlled by the human player**. Bram, Vex, Mira and Lyra are AI-controlled party members, acting independently on their own initiative turns with their existing class-based behavior. The experimental manual-companion-control and independent companion level-choice changes have been canceled. Hero level-up choices remain available as before. Procedural expedition equipment drops, sound, and other v0.9 features remain. This decision supersedes the earlier full-party manual combat-control section above.

## Autonomous NPC class progression (v0.9 preview, 2026-11-18)

Kael remains the only player-controlled combatant. All four named companions independently choose one of their own class's two level-up options at every attained level, including levels already reached in existing saves. Choices are randomized once and saved under `npcLevelPicks`, keyed by companion identity, including companions currently outside the party. They remain permanent across party swaps, save/load, and expeditions. Companion sheets display every selection. Passive HP, AC, melee attack/damage, spell attack/damage, damage reduction and Rogue Sneak Attack dice bonuses are applied in combat. Companion AI can use learned Fighter/Rogue combat techniques, Wizard offensive/area spells, and Cleric healing/support/offensive spells. NPC behavior is automatic; the player cannot select their paths or command their turns. Existing saves are migrated without reset. No claim of browser playtest verification; use TESTING.md. This replaces the earlier canceled *manual companion control* plan, not the AI-party design.
