# Submission

- **Name:** Pedro Pablo Restrepo
- **Email:** pedroprestrepol@gmail.com
- **Time spent:** 

## What I designed
I designed an additional layer to the combat system that introduces two mechanics aimed at making combat decisions more meaningful: Elemental Matchups and Elemental Debuffs.

Each Unit and Enemy has an elemental affinity: Fire, Ice, or Poison, forming a Rock-Paper-Scissors-style triangle where each element has an advantaged, disadvantaged, and neutral matchup. This encourages roster diversity and strategic team composition for each encounter.

Elemental Debuffs add another layer of decision-making by giving each element a unique status effect, encouraging players to consider not only which element to use, but also when and how to use it.

## Key balance changes (and why)

## How to reproduce my results

```bash
python3 sim/simulate.py --units output/units.balanced.csv
```

## Trade-offs

## Checklist

- [x] `output/GDD.md` — one core system, scoped to combat
- [ ] `output/units.balanced.csv` — rebalanced roster
- [ ] `output/BALANCE_REPORT.md` — diagnosis + ≥2 iterations + before/after sim output
- [ ] `output/DESIGN_AI_WORKFLOW.md` — how I used AI
- [ ] No unit is an auto-include or a trap pick
