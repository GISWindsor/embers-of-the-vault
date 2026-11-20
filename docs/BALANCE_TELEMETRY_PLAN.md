# Balance telemetry — isolated test branch

This branch is dedicated to **instrumented balance testing**. It is **not intended for merge into `main`** or inclusion in the public game.

## Implementation contract

- Instrument the actual game logic in the authoritative standalone `index.html`, not only the separate `game.js`.
- Telemetry must be **opt-in**, with no change to RNG, action order, AI, combat rules, rewards, or save behavior when disabled.
- Maintain a distinct campaign/run identifier for each save slot and new campaign; never mix campaigns or retries.
- Persist a versioned telemetry record in browser-local storage and recover after refresh, while retaining enough data to export if a campaign ends.
- Record per-encounter attempts, expedition/stage, enemy roster and initial stats, rounds, result, hero and companion snapshots, effective and raw damage, effective healing, attacks/hits/crits, ability use and action costs, knockouts, potions, rest, XP, silver, loot and level choices.
- Capture a **level-entry snapshot** and **level-exit snapshot**, including HP, AC, attack/spell bonuses, equipment, companions and abilities. Associate encounters with the level at which they were actually fought.
- Avoid counting overkill as effective damage, overheal as effective healing, and restarts as separate victories.
- Add a compact testing panel with recording state, current run, encounters recorded, last event, and **Export JSON**. Provide a readable summary, but do not fabricate 1–7 power ratings; relative balance judgments require analysis.
- Include schema version, game build/commit, timestamps, campaign mode, route and equipment context. Export should contain no secrets or identifying browser data.
- Do not upload telemetry automatically or send it to any server.
- Use an isolated preview URL for this branch, not the public root game.
- Verify disabled-mode behavior, Normal and Iron Man outcomes, refresh/resume, slot replacement, retry handling, level transition, boss completion, and a full export/import parse test.

## Release isolation

- Do **not** merge this branch into `main` by default.
- Do **not** repoint the public game's main URL at this branch.
- If main gameplay fixes are needed, implement them on a separate normal feature branch and selectively bring them into telemetry.
- Before a long test, validate telemetry on a short Expedition 1 run.

## Repository consolidation prerequisite

The current gameplay consolidation PR is [#20](https://github.com/GISWindsor/embers-of-the-vault/pull/20). It currently reports merge conflicts. This telemetry branch was created from `main` to isolate work, **not** to imply PR #20 has merged. Reconcile gameplay changes before relying on this branch for definitive balance measurements.
