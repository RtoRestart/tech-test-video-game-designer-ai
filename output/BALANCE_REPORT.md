# Balance Report 📝
## 1. Diagnosis
*which units are broken and why, with numbers from the simulator (not vibes).*

With the information gather from the Simulation using the initial stats for the units we can determine the following:
- All units require some tweaks to their stats to make their win% close to a 50% and to tighten the win%/cost
- Ser Halden is currently the most overpowered unit, it has a 78.4% win rate and it only costs 6, on the other hand Pyraxis is useless right now, despite having the highest cost of all units it has the lowest win rate,
  this makes Ser Halden the current Auto-pick and Pyraxis the trap pick, with its high cost making players think its really strong when in its current state isn't.
- Brennan is the most balanced unit right now, it has a win% of 51.2% and a win%/cost of 9.32, I still want to tweak this unit a little bit and see if I can get it closer to 50 while also increasing the cost a little bit so that the win%/cost gets to around 10
- We can use the win%/Cost to determine the order in units from most powerful to less, this will help us determine by how much we need to adjust the stats of each unit
 1. Ser Halden (Knight)
 2. Wisp (Cleric)
 3. Rookwood (Myrmidon)
 4. Brennan (Soldier)
 5. Sable (Archer)
 6. Pyraxis (Battlemage)
## 2. Changes
what you changed and the reasoning per change.

## 3. Before/After
simulator output showing the roster moved toward your target (e.g. tighter win-rate spread, flatter cost-efficiency). Show at least two iterations — your first fix will not be your last.

### 3.1 Before
| Unit       | Class      | Cost | Win % | Win % / Cost |
| ---------- | ---------- | ---: | ----: | -----------: |
| Ser Halden | Knight     |    6 | 78.4% |    **13.07** |
| Rookwood   | Myrmidon   |    7 | 65.3% |         9.33 |
| Wisp       | Cleric     |    4 | 51.2% |    **12.79** |
| Brennan    | Soldier    |    5 | 46.6% |         9.32 |
| Sable      | Archer     |    5 | 35.0% |         7.00 |
| Pyraxis    | Battlemage |    9 | 23.5% |     **2.61** |

### 3.2 After (Version 1)

### 3.3 After (Version 2)

## 4.Limitations
what the duel model can't see (positioning, range, healing-as-support) and how you'd validate those.
