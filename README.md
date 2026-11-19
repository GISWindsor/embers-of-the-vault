# Embers of the Vault

**Embers of the Vault** is a free, dependency-free, browser-based tactical RPG inspired by Pathfinder Second Edition (PF2e). It uses original, simplified rules rather than implementing the full tabletop system.

- **Play the main game:** https://giswindsor.github.io/embers-of-the-vault/
- **Play the development preview:** https://giswindsor.github.io/embers-of-the-vault/preview/
- **Repository:** https://github.com/GISWindsor/embers-of-the-vault

## Current project status — November 19, 2026

The latest gameplay development has been consolidated into **`main`**, including the Barbarian class, compact camp layout, autonomous companion progression, equipment tiers, and variable-size expedition and ambush encounters. All existing feature branches were checked after consolidation: **none has commits ahead of `main`**.

This is a playable prototype, not a finished or fully balanced release. Recent encounter-size, Barbarian, and compact-camp changes are **published but still need manual browser playtesting**. The historical v0.9 preview/PR status in earlier README revisions is superseded by the consolidation.

## Getting started

Open either game link in a modern browser, or open the self-contained `index.html` locally. There is no install, dependency download, or build step. Choose a hero class, select **two companions**, and start an expedition.

Campaigns are saved in **three browser-local save slots**. They are not cloud-synced: a different browser, device, private session, or cleared site data may not have your saves. Older single-slot saves are migrated to slot 1 where available.

## Hero classes

| Class | Role and key abilities |
| --- | --- |
| **Barbarian** | High-damage melee attacker. **Power Strike** replaces normal Strike and costs **1 action**. **Reckless Attack** costs **2 actions**, attacks with advantage, and deals **2.5× damage** on a hit; enemy attacks against the Barbarian have advantage until the start of the Barbarian's next turn. Cannot raise a shield, throw fire flasks, or drink healing potions. Base AC **15** before level, equipment, and feat bonuses. |
| **Fighter** | Durable martial combatant with Power Attack and unlockable defensive or multi-target techniques. |
| **Rogue** | Mobile attacker with Sneak Attack and progression choices for precision damage or debuffs. |
| **Cleric** | Healing, protection, and divine offensive abilities; can specialize in Restoration or Judgment. |
| **Wizard** | Offensive magic with Force Barrage, elemental area attacks, and single-target afflictions. |

Hero progression runs through **levels 1–10**. Each level offers two class-specific permanent choices; select one before continuing when a level choice is due. At key levels, choices unlock class techniques or spells. Some previously saved choice IDs now map to revised abilities, so older builds should be checked after loading.

## Combat

- **Three-action turns** with Stride, attacks, class abilities, consumables, and other available actions. Abilities can cost one or two actions.
- **Isometric grid** with obstacles, positioning, attack rolls, critical hits, multiple attack penalties, and simplified tactical rules.
- **One player-controlled hero.** Companions and enemies act automatically on their own initiative turns; initiative is rerolled each round.
- **Four available companions:** Bram (Fighter), Vex (Rogue), Mira (Cleric), and Lyra (Wizard). Choose two for the active party.
- **Autonomous companion development:** Companions gain their own saved, randomized class progression choices, even when not in the active party. Their combat AI uses learned abilities.
- **Party defeat** occurs when all allied combatants fall.
- **Separate melee and spell statistics**, dice breakdowns in the combat log, and distinct hit, miss, and critical-hit sounds when sound is enabled.
- **Targeting previews** for ranged and area attacks. Wizard Force Barrage remains an unlimited, automatically hitting spell that scales with level.
- **Healing Potions** scale by level and normally cost one action; the Barbarian cannot use them.

Sound is optional and off by default. Effects and short victory/defeat tunes are synthesized in the browser; no external music files are required.

## Expeditions and encounters

Expeditions have **five stages** with alternate destinations, terrain, enemy compositions, XP, silver, and equipment rewards. Completing an expedition allows another while retaining the party's level and persistent resources.

**Regular expedition battles and supply-search ambushes can contain 1–10 enemies.** Encounter generation uses a range of compositions, from one powerful foe to a swarm of weak foes:

- Solo enemies receive substantially higher HP, stronger attacks, and better defenses.
- Larger groups have lower individual HP, attack, defense, and damage.
- Groups of five or more have reduced actions per enemy to help control action-economy pressure.
- Encounter stats continue to scale with player level. Generated compositions remain stable for a given expedition node or saved ambush.

The system aims for **roughly comparable encounter difficulty**, not identical challenge across every composition. Its balance still needs playtesting, particularly for solo enemies and groups of 8–10.

## Camp, exploration, and ambushes

The camp screen now uses **collapsible sections** for routes, exploration, merchant, character information, level-up choices, equipment, and companions. Main adventure actions stay accessible in a compact sticky bar.

- Choose the next route on the world map.
- Scout with a limited budget (**two scouting opportunities per campaign**) and retain discovered intelligence.
- Search for supplies to find silver, possible consumables, and rare equipment.
- Supply searches have a **30% ambush chance**. An ambush warning appears; confirming it enters combat directly without allowing a rest or preparation detour. Pending ambushes can resume without requiring outstanding level picks.
- Defeating an ambush awards normal encounter rewards and an additional recovered-supplies cache; losing does not grant that cache.

Supply results appear in a dedicated in-page popup. Ambushes use the same variable-size encounter balancing as regular expedition fights.

## Economy, equipment, and saves

- Earn **XP and silver** through battles, with additional rewards from searches and exploration.
- Visit the **traveling merchant** for Healing Potions, Fire Flasks, and Vitality Tonics.
- Collect equipment across **five tiers** unlocked at levels **1, 3, 5, 7, and 9**: Worn, Forged, Enchanted, Runic, and Legendary.
- Each tier includes a **Vanguard Blade** (melee), **Guardian Armor** (defense), and **Mystic Focus** (spellcasting). Legacy equipment remains supported.
- Equip weapon, armor, and focus items at camp. Equipment affects subsequent combat stats.
- Normal expedition victories have a **45%** equipment-drop chance; final-stage victories guarantee an eligible unowned item when available. Successful supply searches have an **8%** chance of an eligible unowned item. Items are not duplicated once acquired.
- Save data preserves hero progression, companion development, equipment, inventory, silver, and expedition progress.

## Controls and rules scope

Select available actions and board tiles using mouse or touch. The game uses a simplified three-action tactical ruleset: it does **not** reproduce all PF2e conditions, spell saves, reactions, character-building options, or movement rules. For example, most offensive spells use attack rolls against AC, and movement is simplified for the grid.

## Repository layout

| File / path | Purpose |
| --- | --- |
| `index.html` | **Authoritative self-contained main game** served from the repository root; includes inline CSS and JavaScript. |
| `game.js` | Separate game logic file retained in the repository. **Do not assume it contains every latest inline gameplay change** without checking. |
| `style.css` | Separate stylesheet retained in the repository; the standalone HTML also has inline styles. |
| `preview/index.html` | GitHub Pages preview redirect. |
| `preview/branches/feature--barbarian-class/index.html` | Current preview build used by the redirect; the directory name is historical. |
| `TESTING.md` | Playtest records and outstanding checks. Some historical test descriptions may predate the latest balance changes. |

**Important:** The main standalone `index.html` and the published preview currently contain the consolidated game. The separate `game.js` and `style.css` files should be reviewed before using them as a source of truth for new development.

## Development and release workflow

1. Start new development from the latest **`main`**.
2. Implement a change on a short-lived branch.
3. **Publish the actual playable change to `/preview/`** before asking for a playtest. Merely pushing the feature branch does not update the playable preview.
4. Test the change in a browser and record **PASS**, **FAIL**, or **TEST LATER** in `TESTING.md`. Do not mark untested checks as passing.
5. After approval, merge the tested change into **`main`** and keep the public game synchronized.
6. Confirm no unfinished feature branch is ahead of `main` after consolidation.

The preview URL currently redirects into a historically named feature directory; this does **not** mean the branch is ahead of `main`. A future maintenance improvement would be to publish previews to a neutral, stable directory name.

## Current playtest priorities

- Verify Barbarian Power Strike, **2-action** Reckless Attack, vulnerability, class restrictions, and level-up options.
- Compare difficulty and turn pacing for **one strong enemy** versus **8–10 weak enemies**, in both expedition battles and supply-search ambushes.
- Verify the compact camp sections, sticky actions, and mobile scrolling.
- Verify ambush warning → direct combat, pending ambush recovery, and post-victory supply results.
- Recheck existing saves, companion AI/progression, loot, equipment bonuses, and the three save slots.

For historical test results and remaining regression checks, see [TESTING.md](TESTING.md).

## In development: expedition variety and signature bosses

The `feature/expedition-variety-bosses` branch is published to the [development preview](https://giswindsor.github.io/embers-of-the-vault/preview/) but is **not yet merged into the main game**.

- New expeditions select one of four route-width patterns: **fork, hub, gauntlet, crossroads**. The map identifies combat, merchants, shrines, caches and bosses.
- Some intermediate combat nodes are replaced with **noncombat stops**. Visiting a stop advances the expedition without a battle. Hidden caches award silver. Shrines offer full-party restoration for 35 silver.
- Traveling Merchant stops offer **guaranteed, unowned, level-eligible equipment** priced at 45 + 35 × item level silver. The regular camp merchant still sells consumables.
- Every generated expedition ends with one of three distinct bosses: **Ashen Warlord** (up to two reinforcement waves), **Cinder Oracle** (telegraphed round-delayed area hazard), or **Vault Sentinel** (close-range lair tremor). Bosses become stronger at half HP and award additional XP/silver.
- Existing saved expedition node structures remain usable; new layouts and special bosses appear on newly generated expeditions. This is an initial implementation and has not yet received browser verification.

Historical checklist entries were closed as active assignments by the project owner; no replay of the prior baseline checklist is requested.
