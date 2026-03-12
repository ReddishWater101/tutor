# L05 Personnel Requirements
## Parking Lot 
- ADAAG accessible spaces: 1–25→1, 26–50→2, 51–75→3, 76–100→4, 101–150→5, 151–200→6, 201–300→7, 301–400→8, 401–500→9, 501–1000→2%, 1001+→20+1 per 100 over 1000
- Compact SW = 8'0", Handicapped SW ≈ 12'
- Net area = usable space, Gross area = all space (incl. unusable)
- Width = horizontal, Depth = vertical
### Step 1: Determine number of spaces by type
- Total spaces = all cars to park (employees, customers, etc.)
- Compact spaces ≈ 75% of compact car % (conservative — not all compact cars use compact spots)
- Standard spaces = Total − Compact
- Accessible spaces: look up Total in ADAAG 4.1.2 table to get required count
### Step 2: Determine space per automobile
- Pick config: W4 (no walls), W3 (one wall), W2 (two walls)
- Pick parking angle θ (90° = perpendicular, or angular e.g. 60°)
- Look up MW (module width) from the table for both standard SW (given in problem) and compact SW (8'0" from table). Modules stack along depth (on top of each other), cars stack along width (side by side)
- **If 90°:** PW = SW (PW = horizontal width per stall along the row)
- **If angular:** PW = SW / sin(θ), and y = SD × cos(θ) (SD = stall depth, y = horizontal space lost once per row due to angle). Compute PW and y separately for compact and standard
### Step 3: Figure out how many modules of each type & check fit
- Cars per row: round down(W / PW) for 90°, or round down((W − y) / PW) for angular — where W = lot width. Use the matching PW for each type (compact vs standard)
- Each double-loaded module = 2 rows, so cars per module = 2 × cars per row
- Compact modules needed = round up(compact spaces from Step 1 / cars per compact module)
- Standard modules = remaining modules (total modules − compact modules)
- **Depth check:** sum of all module MWs ≤ lot depth (e.g., 2×MW_std + 1×MW_compact ≤ depth). If it doesn't fit, try fewer modules or a different angle
### Step 4: Adjust for accessible & circulation
- Circulation lanes (~14' each side): deduct from interior rows that vehicles must pass through to reach other rows. Edge rows typically don't need circulation
- Accessible spots (SW ≈ 12' each): subtract accessible width from W in that row, then fit remaining with normal PW
- Max cars per row (no adjustments) = round down((W − y) / PW)
- Max cars per row (with circulation) = round down((W − y − 2×14) / PW)
- Max cars per row (with accessible) = round down((W − y − #accessible × 12) / PW)
### Step 5: Compare & select best layout
- If accessible placement is flexible, compute total spaces for each option (e.g., accessible in standard module vs. compact module) and pick the one yielding more total spaces
- Consider module arrangement constraints (e.g., compact not in middle)
## Other
- **Restrooms:** within 200' of every permanent workstation; decentralized > centralized. Sizes: toilet=2.5'×5', sink/urinal=3'×2', entrance/exit=15 ft². Doorway must block interior visibility when open.
- **Food Services:** Vending machines: 1 ft²/person, <200 employees. Serving lines: ≥200, full kitchen benefits at lower cost. Full kitchen: ≥400, high mgmt cost. Within 1000' of all workstations, centrally located. Eating shifts: only 2/3 of shift = actual eating.
- **Health Services:** minimum first-aid room: kit, bed, 2 chairs, ≥100 ft². Located near most hazardous tasks.
- **Barrier-Free (ADA):** reach range 3–4' above floor. PWD clearance 2'3"–2'5" wheelchair breadth. Aisle width ≥5'3" for turning diameter.
- **Office Spaces:** Closed = floor-to-ceiling walls, privacy. Open = no walls, better communication/flexibility/cost, but noisy. Activity-based = different settings per task, agile, saves cost, but loss of identity.


# L06 Evaluating & Selecting Plans
- **CRAFT objective:** min z = ΣᵢΣⱼ fᵢⱼcᵢⱼdᵢⱼ (f = flow loads/time, c = cost per load·dist, d = distance)
## Weighted Factor Comparison
1. Weights for each factor are given in the problem (they sum to a fixed total, e.g., 100)
2. Rate each alternative on every factor — same scale (e.g., 1–10), same polarity (higher = better for all)
3. Score = Weight × Rating per cell. Total each alternative's scores. Pick highest total.
## AHP
- **Build A** (n×n): diagonal = 1. Comparisons needed = n(n−1)/2. Scale: 1=equal, 3=slight, 5=more, 7=strong, 9=absolute. Say k is preferred over j with value x:
```
    j   k        j    k
j [ 1  ___ ]  j [ 1  1/x ] ← loser gets fraction
k [___  1  ]  k [ x   1  ] ← winner gets whole #
```
- **Normalize:** divide each entry by its column sum → A_norm (if A_norm given, start here)
- **Priority vector w:** average each row of A_norm. Entries sum to 1
- **Single criterion:** w is your answer — pick largest w_j
- **Multiple criteria:**  Build S by adding together w1,w2,wN
```
w₁ = | A₁ |   S = | A₁ A₂ A₃ |
     | B₁ |       | B₁ B₂ B₃ |
     | C₁ |       | C₁ C₂ C₃ |
```
  Then: build A_comparion → normalize → average on the criteria themselves → w_comparison. Final answer: v = S·w_comparison → pick largest vᵢ
- **Matrix multiplication:**
```
| a b c |   | x |   | ax+by+cz |
| d e f | × | y | = | dx+ey+fz |
| g h i |   | z |   | gx+hy+iz |
```
- **Real values:** when you have actual numbers instead of 1-9 scale, build A using ratios. E.g., health scores 89 vs 95 (bigger = better): a₁₂ = 89/95 = 0.94, a₂₁ = 95/89 = 1.07. If smaller = better (e.g., commute times): flip it — a₁₂ = x₂/x₁. Then normalize & average as usual
