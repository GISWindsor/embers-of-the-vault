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
