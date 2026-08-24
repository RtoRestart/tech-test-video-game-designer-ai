# Hollow Crown - Elemental Advantage System 🔥


## 1. Overview 📘
The Elemental Advantage System adds an additional layer of complexity and decision-making to combat by introducing three elements that interact through a rock-paper-scissors-style counter triangle.

Each element is strong against one element and weak against another, encouraging players to consider elemental matchups when choosing which units to deploy and which enemies to engage.

Fire > Ice > Poison > Fire

| Element | Strong Against | Weak Against |
|---------|----------------|--------------|
| Fire 🔥 | Ice            | Poison       |
| Ice 🧊  | Poison         | Fire         |
| Poison 🧪| Fire           | Ice          |

Elemental advantage modifies the effectiveness of attacks based on the interaction between the attacker's element and the defender's element. In addition, elemental attacks have a chance to inflict a unique debuff on the target, with each element having its own effect. These debuffs and their effects will be explained in a later section.
This system is designed to add an additional layer of decision-making to combat without replacing or overriding the existing physical/magic distinction.


## 2. Why / Design Goals ❓
- Adds meaningful decision-making by encouraging players to evaluate the battlefield and enemy composition before attacking, rather than simply selecting the unit with the highest expected damage.
- Encourages roster diversity by requiring players to evaluate their available units against upcoming enemies and adjust their roster to gain favorable elemental matchups. This encourages players to
  experiment with different units instead of relying on the same party throughout the entire game.
- Maintains a symmetrical system where each element has one favorable matchup, one unfavorable matchup, and one neutral matchup. This prevents any single element from becoming universally superior.
- Introduces elemental debuffs that add another layer of tactical decision-making. Players can strategically stack or apply debuffs to enemies to increase their party's overall damage output and create more effective attack sequences.
- Creates opportunities for future systems by establishing a foundation for mechanics that interact with elemental debuffs. For example, a potion system could later allow players to remove
   negative debuffs from their heroes, creating additional strategic choices around item usage and resource management.

## 3. Changes to Combat ⚔

### 3.1 Elemental Affinity ⚛️
Each unit and enemy is assigned a permanent elemental affinity that determines which element they are strong against and which they are weak against. An elemental affinity cannot be changed during combat.

PD: Although it would be pretty cool to have a boss that changes its elemental affinity every time it is attacked :D, I think there is a boss like this in Sea of Stars or Expedition 33 if I remember correctly

### 3.2 Advantage / Disadvantage Modifier 🌟
| Matchup     | Damage Modifier |
|-------------|-----------------|
| Advantage   | ×1.25           |
| Neutral     | ×1.00           |
| Disadvantage| ×0.75           |

- **Example:** (Fire → Ice = ×1.25) (Poison → Ice = ×0.75)

### 3.3 Damage Resolution 💥

the Elemental modification occurs after the base damage calculation:
- base_damage = max(1, attacker.power - target.defense)
   
- elemental_damage = base_damage × elemental_modifier
The resulting value is rounded to the nearest whole number.

Critical hits continue to multiply the resulting damage.

  **Proposed order:**
  1. Accuracy check
  2. Base damage calculation
  3. Elemental advantage/disadvantage modifier
  4. Critical calculation
  5. Apply final damage

  This keeps the elemental system separate from accuracy and speed while allowing it to interact naturally with critical hits.



### 3.4 Elemental Debuffs 🔻
| Debuff     | Effect | Lasts |
|-------------|-----------------|-----------------|
| Burning 🔥 | Take 1 damage at the end of every turn  | 3 turns
| Frostbite ❄ | Reduce spd stat by 2                  | 4 turns
| Poisoned ☣️ | take 2 damage every time you move      | 2 turns

### 3.5 Debuffs Chance 🍀
Debuffs have a chance to be applied when an attack has an elemental advantage, such as Fire attacking an Ice target. The chance of applying a debuff is determined by the Luck (LCK) of both the attacker and the target.

Debuffs can only be applied when the attacker has an elemental advantage. Neutral and disadvantaged matchups cannot inflict elemental debuffs. For example, a Fire attack cannot apply the Burning debuff to another Fire-affinity unit.

The following formula determines the debuff application chance:
- ***debuff% = clamp(10 + attacker.lck - target.lck, 5, 25)***

Note: The 5% minimum ensures that debuffs are never completely impossible, while the 25% cap prevents high-Luck units from becoming too reliable at applying debuffs.
| LCK Difference | Debuff Chance |
|----------------|---------------|
| -5             | 5%            |
| -2             | 6%            |
| 0              | 10%           |
| +2             | 14%           |
| +5             | 20%           |
| +10            | 30%           |

## 4. Changes to Units 👤
| Unit | Class | Element |
|------|-------|---------|
| Rookwood | Myrmidon | Fire 🔥  |
| Pyraxis | Battlemage | Fire 🔥 |
| Ser Halden | Knight | Ice 🧊 |
| Wisp | Cleric | Ice 🧊 |
| Brennan | Soldier | Poison 🧪  |
| Sable | Archer | Poison 🧪|

## 5. Changes to Enemies 💀
| Enemy | Element | Encounter Area |
|-------|---------|----------------|
| Gate Wretch | Fire 🔥 | The Sunken Gate |
| Bog Acolyte | Poison 🧪 | The Sunken Gate |
| Throne Guard | Ice 🧊 | The Hollow Throne |
| Crown Magus | Ice 🧊 | The Hollow Throne |


## 6. Feedback / UI 📣
### 6.1 Unit & Enemy Affinity 👥
The unit's elemental affinity should be visible on:
- Unit / Enemy information panel
- Battlefield unit frame
- Deployment screen

Each element should have a distinct icon and visual treatment.

### 6.2 Attack Preview and Reinforcement
Before an attack is confirmed, the combat preview should clearly communicate the elemental interaction to the player.

Example:

FIRE → ICE = ADVANTAGE

The elemental matchup is reinforced through both visual and audio feedback:

- **🟢 Advantage:** A positive reinforcement sound effect plays, accompanied by a "Super Effective!" message that briefly appears on screen.
- **⚪ Neutral:** No additional sound effect or text is displayed, keeping the feedback unobtrusive when there is no elemental interaction.
- **🔴 Disadvantage:** A negative reinforcement sound effect plays, accompanied by a "Not Very Effective" message that briefly appears on screen.

This feedback should allow players to quickly understand the effectiveness of their attack without requiring them to memorize or manually calculate the elemental relationships.


## 7. Edge Cases 🔪
| Edge Case | Rule |
|-----------|------|
| Multiple hits with elemental modifier | Each individual strike receives the applicable elemental modifier. |
| Critical hits with elemental modifier | The elemental modifier is applied first, then the critical multiplier is applied. The final damage value is rounded afterwards. |
| Elemental modifier reduces damage below 1 | Damage can never be lower than 1. If the modified damage falls below 1, it is rounded up to 1. |
| Missing elemental data | All units should have an assigned elemental affinity. If a unit has no affinity assigned, a random element is assigned to prevent errors or crashes. |
