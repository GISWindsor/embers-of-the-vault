# Archived playtest — version reference

- **Test date:** 2026-11-19
- **Mode:** Normal only
- **Tested preview:** https://giswindsor.github.io/embers-of-the-vault/preview/branches/feature--expedition-variety-bosses/
- **Development code snapshot before playtest:** [`3c90be4c37a587d2d2cfd197aff03424958ff93a`](https://github.com/GISWindsor/embers-of-the-vault/commit/3c90be4c37a587d2d2cfd197aff03424958ff93a)
- **Preview publication commit:** [`d460a09a800365b85714c0b69d96153c1c472a84`](https://github.com/GISWindsor/embers-of-the-vault/commit/d460a09a800365b85714c0b69d96153c1c472a84)
- **Provenance:** Work browser playtest report supplied by project owner; recorded observations, not independently reproduced in this archive operation.
- **Scope:** Five Expedition 1 completions and one Expedition 2 opener; not a full level-10 test.

---

# Embers of the Vault — Normal Mode playtest

## Executive summary

**All five classes defeated an Expedition 1 boss and reached the “Expedition Complete!” screen.** Across the five campaigns, I recorded **25 Expedition 1 encounters, 16 victories, and 9 defeats**. I retried every defeat through the Normal Mode campaign flow. The Cleric also won the opening fight of Expedition 2. I played Normal Mode exclusively and made no source or repository changes.

Three findings stand out:

1. **The Oracle’s positioning mattered more than another point of AC.** The Fighter lost three times while stalled near central cover. Taking the open lower flank on attempt four let him reach melee, reduced the fight from 10–13 rounds to five, and secured the win. The Rogue used the same approach and won with the entire party at full HP.
2. **Noncombat routes create a real progression tradeoff.** The Barbarian and Cleric reached the boss at **level 1 with 400 XP**. The Barbarian required five attempts against the Warlord, while the Cleric beat the Oracle on the first attempt. The new readiness warning correctly flagged the Cleric’s level and XP. The clearest design opportunity is to give players an actionable choice when the warning appears.
3. **Companions kept fights winnable after a hero knockout.** Bram and Mira finished the Warlord after the Barbarian fell. Bram and Mira also finished the Oracle after the Wizard fell. That made both fights feel recoverable. It also means that a hero’s win rate alone can overstate how much that hero contributed.

## Class comparison

The Fighter and Barbarian totals include the earlier Normal Mode encounters from the saves I resumed. **Logged damage includes overkill and is not capped at the target’s remaining HP.** The first Fighter ambush had no retained damage tally.

| Hero | Encounters | Wins–losses | Win rate | Boss wins / attempts | Expeditions cleared | Logged damage dealt / received | Hero / companion knockouts | Potions / rests | Level, XP, silver at clear |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---|
| Barbarian | 6 | 2–4 | 33% | 1/5 | 1 | 539 / 548 | 6 / 9 | 1 / 1 | 2, 1,540 XP, 343 sp |
| Fighter | 9 | 4–5 | 44% | 1/4 | 1 | 599 / 765 over 8 fights | 5 / 11 | 4 / 1 | 3, 2,200 XP, 377 sp |
| Rogue | 4 | 4–0 | 100% | 1/1 | 1 | 371 / 120 | 0 / 0 | 2 / 0 | 3, 3,040 XP, 443 sp |
| Cleric | 2 | 2–0 | 100% | 1/1 | 1 | 162 / 111 | 0 / 1 | 3 / 1 | 2, 1,540 XP, 300 sp |
| Wizard | 4 | 4–0 | 100% | 1/1 | 1 | 271 / 178 | 1 / 3 | 3 / 1 | 3, 2,900 XP, 436 sp |

| Hero | Average logged damage dealt / received | Highest recorded hit dealt / received | Criticals dealt / received | Mean party HP at outcome | Boss rounds on clear |
|---|---:|---:|---:|---:|---:|
| Barbarian | 89.8 / 91.3 | 50 / 27 | 4 / 8 across 3 captured attempts. Full total **Not recorded** | 14.0% | 4 |
| Fighter | 74.9 / 95.6 | 40 / 30 | 3 / 16 across 6 captured fights. Full total **Not recorded** | 36.5% | 5 |
| Rogue | 92.8 / 30.0 | 34 / 28 | 6 / 1 | 99.6% | 5 |
| Cleric | 81.0 / 55.5 | 13 / 18 | 0 / 1 | 68.5% | 7 |
| Wizard | 67.8 / 44.5 | 18 / 22 | 2 / 8 | 59.3% | 6 |

Party HP is measured from the combat roster at the outcome, before camp recovery or level-up HP. A total party wipe contributes 0%. Knockouts include heroes and companions who fell during a victory and returned at camp. These were single campaigns with different routes, parties, and bosses. The Rogue had the cleanest run observed, but the results do not establish a five-class power ranking.

## Detailed class analysis

| Hero | What worked | Main weakness observed |
|---|---|---|
| **Barbarian** | Savage Endurance gave the hero 34 starting HP. Power Strike produced useful damage without exposing the hero to advantage. Reckless Attack killed an Ashen Brute for 30 and landed a 50-damage boss critical. Bram and Mira gave the party enough damage and staying power to finish the successful attempt after Kael fell. | Against the Warlord, using Reckless early could give a dangerous enemy multiple advantaged attacks. After the 50-damage hit, the Warlord answered with two 22-damage criticals. The Barbarian fell in all six fights, including both victories. |
| **Fighter** | Powerful Strikes and Guarded Advance worked well once the hero reached the target. A 40-damage Power Attack critical ended the Catacombs retry. Lyra dealt ranged damage during the Oracle pursuit, and the Fighter finished the winning attempt at 32/32 HP. | The slow Oracle attempts were dominated by pursuit and repeated sigil damage. A shield helped during idle turns, but taking the lower flank was the decisive adjustment. |
| **Rogue** | Sharp Blades, Shadow Guard, and Bram’s positioning made flanking productive. The Rogue logged 191 hero damage across four fights and finished the Oracle with the whole party at full HP. | Obsidian Gate made the party look especially strong, with six low-HP enemies and only 4 incoming damage. The result needs replication against a tougher route and other bosses before changing Rogue damage. |
| **Cleric** | Sacred Guard, Bram, and Vex let the hero cover healing without bringing Mira. The level-1 party cleared the Oracle and then recovered from a low-HP Expedition 2 start through in-combat Heal. | With the hero spending actions on support, the party leaned on Bram for damage. In the first expedition Bram logged 108 damage to the Cleric hero’s 20. That worked with this composition. A lower-damage party remains untested. |
| **Wizard** | Focused Bolts and Mystic Armor supported a ranged approach. Force Barrage kept dealing damage without attack rolls, and the Wizard finished Fallen Watchtower at full personal HP after both companions fell. | The Oracle still knocked the Wizard out. Maintaining distance helped in regular fights, but sigils and ranged attacks could reach the hero. Bram dealt 64 damage in the boss fight and landed the finishing blow. |

**Action economy.** Power Attack showed clear value when a hit could finish a healthy target. Flanking made ordinary Rogue Strikes productive even after the first attack of a turn. Force Barrage was a dependable use of two actions when the Wizard could stay in range. Reckless Attack was most convincing when it removed an enemy or when an ally could carry the next turn. The sample does not support declaring an action universally superior or useless.

## Encounters, bosses, and retry record

| Campaign | Defeats and adjustments | Verified result |
|---|---|---|
| Barbarian | **Warlord #1:** Mira/Lyra, lethal counterattack after Reckless. **#2:** +1 AC armor, Warlord survived at 28/102. **#3:** Bram replaced Mira, Warlord survived at 35/102. **#4:** Mira replaced Lyra, Warlord survived at 20/102. | **#5:** Bram and Mira finished the boss and last raider in round 4. |
| Fighter | **Catacombs #1 and #2:** party wiped with empty bottles. **Oracle #1–#3:** central pursuit stalled, with the boss surviving at 58, 51, and 21 HP. Those fights lasted 11, 10, and 13 rounds. | **Catacombs #3:** Lyra replaced Vex and the Fighter’s Power Attack finished the Warden. **Oracle #4:** lower-flank approach, victory in round 5. |
| Rogue | No defeats. | Oracle cleared on attempt 1, round 5, at 85/85 party HP. |
| Cleric | No defeats. | Oracle cleared on attempt 1, round 7, at 37/73 party HP. |
| Wizard | No defeats. | Oracle cleared on attempt 1, round 6, with the hero down and both companions standing. |

The **Warlord** brought two reinforcement waves and logged criticals up to 27 damage. Those hits could take out a full-health level-1 Cleric or Wizard. The **Oracle** was more sensitive to approach and positioning. The Fighter took 21–27 logged sigil damage in each failed attempt and 9 on the clear. The level-1 Cleric took 27 sigil damage across the party and still won, so the sigil alone did not determine the outcome. **Two boss types were encountered. The third was not recorded.**

The biggest regular-encounter contrast was the Rogue’s **Obsidian Gate** win, with 4 logged damage received, versus the Wizard’s **Fallen Watchtower** win, with 61 damage received and both companions down. Those fights differed in enemies and party setup, so encounter composition is a better lead for follow-up than class tuning.

## XP and resource economy

| Hero | Route and leveling | Equipment and spending |
|---|---|---|
| Barbarian | One route battle, one shrine, two caches, then Warlord. Reached level 2 at the clear. | Acquired and equipped Worn Guardian Armor. Boss awarded Worn Mystic Focus. |
| Fighter | Ambush, two route battles, two shrine nodes, then Oracle. Reached level 2 after Catacombs and level 3 at the clear. | Boss awarded Forged Vanguard Blade. |
| Rogue | Three route battles and a merchant before Oracle. Reached level 2 before the third route battle and level 3 at the clear. | Spent 16 sp on a fire flask. Boss awarded Forged Vanguard Blade. |
| Cleric | One route battle, one cache, two shrine nodes, then Oracle. Reached level 2 at the clear and selected Blessed Armor before Expedition 2. | Equipped the Worn Vanguard Blade awarded by the boss. |
| Wizard | Three route battles and a shrine before Oracle. Reached level 2 after the third route battle and level 3 at the clear. | Boss awarded Forged Mystic Focus. |

Each Expedition 1 boss victory awarded **1,140 XP**. The two low-combat routes cleared at 1,540 XP. The combat-heavy Rogue and Wizard cleared at 3,040 and 2,900 XP. More combat made a visible difference in boss-entry level and the next expedition’s starting power.

Normal defeats restored party HP and let the player retry, while empty potion bottles stayed empty. A shrine restored HP and refilled bottles. That makes shrine placement consequential. The Fighter had no combat potions during the Catacombs losses, and the Wizard entered the Oracle with empty bottles. Both fights were ultimately winnable through party or positioning changes. Exact counts of wounded entries and effective HP restored across all inherited fights were **Not recorded**. Heal totals below are log values, which can include overhealing.

**Expedition 2 spot check.** The Cleric entered Forgotten Reliquary at **46/95 party HP**, with Vex at **1/29** and zero filled bottles. The scouted enemies had 21–23 HP and AC 17–18. The party won in four rounds, ending at **88/95 HP** after three Heal casts logged for a combined 44 HP. The fight awarded 400 XP and 49 silver, bringing the save to **1,940 XP and 349 sp**. This confirms that a wounded party can recover through play when it has a Cleric. It does not establish the difficulty curve for the rest of Expedition 2 or for the other classes.

## Companions and AI

| Hero campaign | Companion damage captured | Companion Heal captured | Companion slots ending upright |
|---|---|---:|---:|
| Barbarian | Bram 65, Mira 30, Lyra 15 across the final three boss attempts | Mira 44 across those attempts | 3/12 |
| Fighter | Lyra 179, Mira 81, Vex 33 across six continuation fights | Mira 145 across those fights | 7/18 |
| Rogue | Bram 147, Mira 33 | Mira 111 | 8/8 |
| Cleric | Bram 108, Vex 34 | Hero Cleric logged 15 in Expedition 1 and 44 in the Expedition 2 opener | 3/4 |
| Wizard | Bram 130, Mira 17 | Mira 68 | 5/8 |

Bram made the biggest difference where someone needed to hold melee contact or finish a boss while the hero was down. Mira provided large Heal rolls and helped the Rogue finish at full HP, but the Cleric cleared with **Bram and Vex**, showing that Mira herself is optional when the hero covers healing. Whether a party can consistently clear without any Cleric remains unverified.

Lyra, Bridge Archers, and enemy spellcasters logged ranged repositioning. Lyra sometimes spent several actions repositioning before casting. I saw no verified instance of a ranged unit unnecessarily choosing melee. Exact useful-versus-wasted action rates and effective healing after overheal were **Not recorded**.

## Bugs, usability, and recommendations

I resumed an already-open Barbarian tab, then reloaded before resuming the Fighter. The reloaded page showed updated defeat text, a disabled empty-potion control at camp, corrected boss scouting on newly scouted Oracle nodes, and the readiness warning. The older Barbarian scouting entry still listed ordinary enemies for Whispering Fen. I could not establish whether a fresh Warlord scout now reports its reinforcement waves.

| Priority | Issue and evidence | Recommended change | Expected impact |
|---|---|---|---|
| **High** | **Oracle pursuit can turn into a stall.** Three Fighter losses lasted 10–13 rounds around central cover. The lower approach produced a five-round clear. | Keep the boss’s damage for now. Make the marked sigil tiles and safe exits easier to read, then retest melee pursuit on maps with central cover. | Keeps movement central to the fight while helping players recognize when to switch lanes. |
| **High** | **The readiness warning arrives after the route has been committed.** The Cleric reached the boss at 400 XP after a cache and two shrines. | Surface readiness when the player can still choose a combat branch. For forced low-combat maps, compare a short optional encounter with granting enough route XP to reach the existing **1,000 XP** level-2 threshold. | Gives players a way to act on the warning and preserves the option to attempt a level-1 clear. |
| **Medium** | **Empty potions still accept clicks during combat.** Reproduced on the Wizard’s Oracle fight with zero filled bottles. Clicking Drink Potion repeatedly logged that the bottles were empty. Camp already showed the disabled empty state. | Apply the camp’s empty-state behavior to the combat control. Display **0/2 filled** when empty. | Removes dead clicks and makes the remaining action choices clearer. |
| **Medium** | **Saved scouting can retain obsolete boss information.** The inherited Whispering Fen entry listed a wolf, archer, and initiate. Fresh Oracle reports matched the boss’s identity, HP, and AC on four nodes. | Refresh stale saved scouting entries when encounter data changes. Verify that a fresh Warlord scout flags **two reinforcement waves**. | Makes scouting dependable on existing saves and provides useful information for party selection. |
| **Medium** | **Warlord burst is severe for level-1 parties.** The Barbarian lost four times and a boss critical reached 27 damage. | Run matched Warlord trials at levels 1 and 2 with the same party and armor. If level-1 wipes remain common after improving route guidance, trial **−1 phase-two attack bonus** before changing HP, damage, or wave count. | Tests a focused reduction in critical-hit frequency while preserving the encounter’s escalation. |
| **Low** | **Board hit testing was unreliable on the earlier build.** A unit HP bar intercepted the center of a highlighted movement tile. Clicking the exposed edge worked. The same overlap was not isolated again after reload. | Add a regression check that clicks the center of a legal tile underneath a nearby HP bar. | Verifies that the input fix holds on crowded boards. |

The most memorable win was the Barbarian’s fifth Warlord attempt. Kael went down, but Bram and Mira finished with **49/49 combined HP**. The most revealing follow-up was the Cleric’s Expedition 2 opener, where a companion carried over at 1 HP and ended the fight at 26. Both outcomes show how much the game’s party systems can reward adaptation. I would prioritize route guidance, combat feedback, and matched boss trials before changing class numbers.