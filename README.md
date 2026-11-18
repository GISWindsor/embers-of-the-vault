# Embers of the Vault — Browser RPG Prototype

A self-contained, no-dependencies isometric tactical combat demo inspired by Pathfinder Second Edition.

## Run

Open `index.html` in Chrome, Firefox, Edge, or Safari. No server or installation is required.

Alternatively, in this directory run `python -m http.server 8000` and open http://localhost:8000.

## Play

- Choose **Fighter, Rogue, Cleric, or Wizard** for Kael before combat. Mira (cleric) and Vex (rogue) are AI companions.
- Each combatant gets **three actions** each turn.
- Select **Stride**, then click a blue tile to move up to four squares (20 feet).
- Select **Strike**, then click an adjacent enemy to attack. Multiple strikes accrue the normal 0/−5/−10 multiple attack penalty.
- **Raise Shield** adds +2 AC until your next turn. **Drink Potion** heals once per encounter.
- The cleric automatically casts a two-action Heal on injured allies.
- Defeat all three enemies to win; if Kael falls, you lose.

## Rules and scope

Includes d20 attack rolls, PF2E's four degrees of success (including natural 20/1 shifts), critical hits at AC+10, multiple attack penalty, flanking/off-guard, shield bonus, turn-based initiative order, and three-action economy. Simplifications: 4-square movement, no diagonal movement, simplified damage and spellcasting, no opportunity attacks, no dying/wounded system, and no full character creation. This is a playable prototype, not a complete PF2E implementation.

## Files

- `index.html` — page layout
- `style.css` — visual design
- `game.js` — combat, pathfinding, AI, SVG map rendering

All art is drawn with SVG/CSS and Unicode symbols; no external assets.

## Class selection (v0.2)

On launch, choose one of four level-1 classes, then click **Enter the Vault**. Restart Encounter reopens the class selector. Fighter gets a two-action Power Attack; Rogue gets passive +1d6 sneak attack against flanked/off-guard foes; Cleric gets a two-action ranged Heal; Wizard gets a two-action ranged Force Barrage. Class stats and action controls update to match the selection. These are prototype approximations, not complete PF2E class implementations. Class selection is per encounter; persistent characters are not yet implemented.
