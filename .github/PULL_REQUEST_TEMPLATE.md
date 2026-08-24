# Submission

- **Name:** Pedro Pablo Restrepo
- **Email:** pedroprestrepol@gmail.com
- **Time spent:** 

## What I designed
I designed an additional layer to the combat system that introduces two mechanics aimed at making combat decisions more meaningful: Elemental Matchups and Elemental Debuffs.

Each Unit and Enemy has an elemental affinity: Fire, Ice, or Poison, forming a Rock-Paper-Scissors-style triangle where each element has an advantaged, disadvantaged, and neutral matchup. This encourages roster diversity and strategic team composition for each encounter.

Elemental Debuffs add another layer of decision-making by giving each element a unique status effect, encouraging players to consider not only which element to use, but also when and how to use it.

## Key balance changes (and why)
rebalanced the Units so that their win%/cost is similar but also rebalanced taking into account enemies encounters and the classes that have extended range, changed battlemage from being a trap pick unit, it's still an expensive cost hero but now it is worth its cost while not being to OP, rebalanced Ser Halden Knight from being an auto-include. now all units have a  WIN%/COST within 7.5 to 8.3. making them all viable options to play with.

## How to reproduce my results

```bash
- To obtain the Version 1 results: go to the python script, and uncomment line 141, and then comment lines 138 and 144
- To obtain the Version 1 results: go to the python script, and uncomment line 144, and then comment lines 138 and 141
```

## Trade-offs

## Checklist

- [x] `output/GDD.md` — one core system, scoped to combat
- [x] `output/units.balanced.csv` — rebalanced roster
- [x] `output/BALANCE_REPORT.md` — diagnosis + ≥2 iterations + before/after sim output
- [x] `output/DESIGN_AI_WORKFLOW.md` — how I used AI
- [x] No unit is an auto-include or a trap pick
