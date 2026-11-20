# Embers of the Vault — Patch Notes & Release History

This is the game's **second README-style document**, dedicated to player-facing changes over time. The main [README](README.md) describes how to play and the current project.

> **Versioning note (November 19, 2026):** GitHub currently has **no formal Releases** listed for this repository. The entries below are **documented release milestones**, not invented semantic-version tags. The repository's commit/PR history is the source of truth. Dates are grouped by the available November 2026 history; exact individual release dates should be verified against their linked commits. **Preview-only changes are not production releases.**

## Released to the main game

### Expedition variety & bosses — November 19, 2026
**Status: released to `main`** — [release commit](https://github.com/GISWindsor/embers-of-the-vault/commit/9583a581) · [PR #17](https://github.com/GISWindsor/embers-of-the-vault/pull/17)

- Introduced varied expedition map layouts, including forks, hubs, gauntlets, and crossroads, with combat, shrines, caches, and merchant stops.
- Added three distinct expedition bosses with phases, lair effects, and bounded reinforcements.
- Committed route selection: selecting one path prevents scouting, searching, or switching to alternatives for that stage.
- Moved shopping to the Traveling Merchant popup, with equipment descriptions; removed the redundant camp shopping panel.
- Presented pending level-up choices in a dedicated popup, including after boss rewards or supply dialogs.
- Improved route-selection wording and expedition map legend.

### Encounter results & Iron Man — November 19, 2026
**Status: released to `main`** — [PR #18](https://github.com/GISWindsor/embers-of-the-vault/pull/18)

- Added a result popup showing combat victory, defeat, and rewards before level-up.
- Added optional **Iron Man** campaign mode with limited resting and permanent defeat.
- Clarified the distinction between forfeiting a run and a defeated Iron Man campaign.

### Refillable healing potions — November 19, 2026
**Status: released to `main`** — [PR #19](https://github.com/GISWindsor/embers-of-the-vault/pull/19)

- Replaced one-off potion purchases with refillable healing bottles and permanent merchant capacity upgrades.
- Added camp potion use and level-scaled healing.
- Allowed Barbarian potion use **outside combat** while retaining its in-combat potion restriction.
- Improved descriptions of potion restrictions.

### Consolidated playable prototype — November 18–19, 2026
**Status: released to `main`** — [consolidation commit](https://github.com/GISWindsor/embers-of-the-vault/commit/0133f628)

- Consolidated previous feature development into the playable main game.
- Five playable hero classes: Barbarian, Fighter, Rogue, Cleric, Wizard.
- Class-specific level-up choices through level 10 and autonomous companion progression.
- Four recruitable companions: Bram, Vex, Mira, Lyra; choose two for an expedition.
- Added multi-tier equipment and persistent inventory, XP, silver, and expedition progression.
- Added variable-size expedition and supply-ambush encounters, from solo elites to groups of up to ten; adjusted enemy stats and swarm action economy by group size.
- Improved Barbarian progression and balance, including Power Strike and two-action Reckless Attack with a vulnerability drawback.
- Streamlined camp with collapsible sections and accessible adventure controls.
- Added expedition scouting, supply searches, and ambush gameplay.
- Preserved three browser-local save slots.

## Development preview updates — not yet documented as main-game releases

These changes were published to a playable **preview** or worked on in a development branch. They should **not** be presented as released to the main game without a subsequent merge.

### Scouting, controls & defeat-message stabilization — November 19, 2026
**Status: development preview** — [preview publication](https://github.com/GISWindsor/embers-of-the-vault/commit/d460a09a)

- Updated scouting to use the actual encounter-generation path, including boss identity and reinforcement information.
- Changed board hit testing so unit artwork and HP bars do not intercept movement-tile clicks.
- Distinguished ordinary defeats, ambush defeats, and permanent Iron Man defeat messaging.
- Made empty potion status clearer at camp.
- Added a warning before entering a boss fight while below level 2.
- **Verification:** JavaScript syntax was checked when published; full browser regression testing was not claimed.

### Endurance, XP & AI balancing — November 19, 2026
**Status: development previews** — [endurance preview](https://github.com/GISWindsor/embers-of-the-vault/commit/10a58f40) · [XP preview](https://github.com/GISWindsor/embers-of-the-vault/commit/e06849f1) · [AI preview](https://github.com/GISWindsor/embers-of-the-vault/commit/c85a0941)

- Iterated Normal and Iron Man endurance balance.
- Revised XP thresholds in the development preview.
- Improved ranged positioning and decision-making for allied wizards and enemy archers/casters.
- Added camp party-HP visibility and shared healing-bottle guidance.

## Playtest evidence (not releases)

- [Five-class Expedition 1 Normal Mode report](docs/playtests/2026-11-19-normal-mode-five-class-expedition-1.md) — all five classes cleared Expedition 1; contains observed balance issues and limits.
- The later level-10 endurance report is a separate test artifact and should be linked here once its complete report has been committed.

## How future entries should work

For every approved production release, add a new section **at the top of “Released to the main game”** containing:

- **Version / release name** and date (use a real tag such as `v0.10.0` only if it exists).
- **Status:** main release, preview-only, or experimental.
- **Added**, **Changed**, **Fixed**, and **Balance** notes, as applicable.
- **Compatibility / save migration** notes when applicable.
- Link to the merge PR, tag, or exact commit.
- Known issues and test coverage when important.

Keep preview changes in the preview section until merged. Do not describe a preview publication commit as a formal GitHub Release.

---

*Historical entries are reconstructed from the repository README, PR merges, and commit subjects. This file intentionally avoids inventing numbered releases where the project has not created release tags.*
