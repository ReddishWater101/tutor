# Cheat Sheet Audit Recommendations

## L05 — Personnel Requirements (70% exam-ready)

CRITICAL
- "75% of compact car %" is cryptic — reword to: Compact spaces = ~75% x (compact car % x total spaces)
- No explicit formula for total modules from lot depth — need: n_std x MW_std + n_compact x MW_compact <= lot depth

MODERATE
- "Edge rows" circulation rule is vague — clarify which rows need it (not first/last physical row)
- Missing "compare both orientations" — add to Step 5: Try swapping lot width<->depth
- Eating shifts formula missing: shifts = floor((window - shift_len) / (2/3 x shift_len)) + 1
- SD (stall depth) — note it's "given in the problem for angular parking"


## L06 — Evaluating & Selecting Plans (70% exam-ready)

CRITICAL
- AHP matrix placement convention — replace with explicit rule: a_jk = x if j preferred, a_kj = 1/x
- Multi-criteria AHP flow is the biggest gap — "adding together w1,w2,wN" is wrong (they're columns of S, not summed). Rewrite to: For each criterion, AHP alternatives -> score vector s. Columns of S = [s1 s2 ...]. AHP criteria themselves -> w. Final: v = S*w, pick largest.

MODERATE
- Clarify that each per-criterion w becomes a column of S
- Real values: simplify to Bigger=better: a_jk = val_j/val_k. Smaller=better: flip
- Matrix multiplication block (6 lines) could compress to 1-2 lines

MINOR
- Typo "A_comparion" -> "A_comparison"


## L07 — Material Handling (90% exam-ready)

CRITICAL
- In/Out should say Inside/Outside for container dimensions

MINOR
- "pallet minus bottom deck" -> "pallet without bottom deck"


## L08 — Warehouse Operations & Layout (75% exam-ready)

CRITICAL
- Tj definition "(double 1-way count)" is misleading — change to (as given)
- pi computation: needs the WHY — recv share = 1/2, ship share = 1/2, then split ship by dock ratio

MODERATE
- Sj: clarify it's (given, or ceil(area/bay area))
- Avg Quantity: formula says "(in units)" but doesn't show the conversion — change to 1/2(OQ days x demand/day) + (SS days x demand/day)
- Shared docks: add the actual formula H_truck = (Nr x Hr + Ns x Hs)/(Nr+Ns)


## L09 — ASRS (65% exam-ready — weakest section)

CRITICAL
- aisle_unit is never defined — add: aisle_unit >= 3 x load_W + 2'
- System Length formula is wrong — uses "load_length" but should be bays/row x (load_W + gap) + crane_clr (crane_clr typically 25')

MODERATE
- L, H in cycle time formulas could be confused with load dimensions — add: L,H = rack length,height (ft)
- TP/D never defined — add: TP/D = time per pickup or deposit op
- hv, vv not defined — add: hv,vv = horiz,vert speed (fpm)


## Space Notes
- Most fixes are rewordings, not additions
- L06 matrix multiplication block can compress from 6 lines to 2, freeing space
- L09 needs ~5 new lines for variable definitions
- Net impact: roughly space-neutral with compression trade-offs
