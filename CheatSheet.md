# L05 Personnel Requirements
## Parking Lot 
- ADAAG accessible spaces: 1–25→1, 26–50→2, 51–75→3, 76–100→4, 101–150→5, 151–200→6, 201–300→7, 301–400→8, 401–500→9, 501–1000→2%, 1001+→20+1 per 100 over 1000
- Compact SW = 8'0", Handicapped SW ≈ 12'
- Net area = usable space, Gross area = all space (incl. unusable)
- Width = horizontal, Depth = vertical (for the lot). But MW (module width) stacks along depth (vertical)
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
- **Restrooms:** within 200' of every permanent workstation; decentralized > centralized. Sizes: toilet=2.5'×5', sink/urinal=3'×2', entrance/exit=15 ft^2. Doorway must block interior visibility when open.
- **Food Services:** Vending machines: 1 ft^2/person, <200 employees. Serving lines: ≥200, full kitchen benefits at lower cost. Full kitchen: ≥400, high mgmt cost. Within 1000' of all workstations, centrally located. Eating shifts: only 2/3 of shift = actual eating.
- **Health Services:** minimum first-aid room: kit, bed, 2 chairs, ≥100 ft^2. Located near most hazardous tasks.
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

# L07 Material Handling
- MH: movement, storage, control, protection of materials through manufacture→distribution→consumption→disposal. ~25% employees, ~55% space, ~87% prod time, 15–70% of product cost
- Product goals: right amount, material, condition, sequence, orientation, place, time, cost, method
- 10 Principles: direct intentional plan, standardization of work, not hurt productivity, good ergonomics, unit load (sized appropriately), space util (3D), consider all connected systems, automation when possible, min environ footprint, total life-cycle cost
- **System Equation:** Materials + Moves + Methods = Preferred System
- What=Materials, Where+When=Moves, How+Who=Methods, Which=Preferred System
- Planning Chart steps: O(operation) T(transport) S(storage) I(inspection). What moved?=Materials | Where/When?=Moves | How/Who/Which?=Methods. Distance only during T steps
- Unitized equipment: Pallet = bottom deck boards, Skid = pallet minus bottom deck, Crate = boxed in totally
## Returnable Containers
- Dimensions: In(Li×Wi×Hi), Out(Lo×Wo×Ho), Nested(Ln×Wn×Hn), Trailer(Lt×Wt×Ht)
- CSU = (Li×Wi×Hi) / (Lo×Wo×Ho)
- CNR = Ho : Hn
- Fit = ⌊Lt/Lo⌋ × ⌊Wt/Wo⌋ × ⌊Ht/Ho⌋
- TSU = Fit × (Li×Wi×Hi) / (Lt×Wt×Ht)
## Equipment Selection
- Fixed path + high volume → Conveyor
- Variable path + restricted area → Crane
- Variable path + unrestricted → Industrial Vehicle
- High invest + future returns → Automated (AGV, AS/RS, monorail)
- Controlled condition needed → Conveyor
- Flexibility needed → Vehicle
- Conveyor types: chute, belt, roller, wheel, slat, chain, towline, trolley, power-and-free, cart-on-track. Speed = StationLength / CycleTime
- Crane types: jib, bridge, gantry, tower, stacker crane
- Vehicles: Walking (hand truck, pallet jack, platform truck, walkie stacker) | Riding (pallet truck, tractor trailer, counterbalanced lift, straddle carrier, mobile yard crane) | Automated (AGV, monorail, sorting transfer)
- Storage: block stacking, selective rack, drive-in/through, flow-through, push-back, sliding, cantilever, stacking frame, shelves/bins/drawers, carousel, AS/RS
- Unit load: single mass; limited by cube (vol) & weight. Methods: lift under, insert into, squeeze, suspend
- Data collection: bar code, RFID, OCR, magnetic stripe, computer vision


# L08 Warehouse Operations & Layout
- Warehouse = storage-heavy | Distribution Center = little/no storage
- Crossdocking: receive → ship directly (no storage, high-vol predictable). Traditional: receive → store → pick → ship
- Receiving = ~10% operating cost | Shipping = ~20% | Warehouse >80% capacity → expand
## Warehouse Functions
- Receiving, Inspection/QC, Repackaging, Put-away, Storage, Order Picking, Postponement, Sortation, Packing/Shipping, Cross-docking, Replenishing
- Repackaging = bulk→single units | Put-away = receiving→storage | Postponement = add labels before ship | Sortation = split mixed picks into orders | Replenishing = refill pick shelves from bulk
## Number of Docks
- N_dock = ⌈Sf × T_day × H_truck / H_day⌉ (round UP)
- Sf = safety factor, T_day = trucks/day, H_truck = hrs to load/unload, H_day = hrs/day
- Not shared: compute N_recv + N_ship separately
- Shared: combine trucks, use wtd avg time, single calc
## Storage Models
- **Dedicated** — fixed slot per SKU, size for MAX inventory. Best throughput (fast movers front). Needs most space
- **Random** — any SKU → nearest open slot, FIFO out. Best space util. Space = max aggregate inventory
- **Class-based** — 3-5 classes by activity/space ratio. Dedicated between, random within
- Reorder Point = (SS days + lead time days) × demand/day
- Max Quantity = (SS days × demand/day) + (OQ days × demand/day)
- Avg Quantity = (1/2)(OQ) + SS (in units)
- Dedicated space = Σ(max inventory per SKU)
- Random space = max aggregate inventory (always ≤ dedicated)
## Layout Principles
- **Popularity** — 85/15 Pareto, fast movers near I/O
- **Similarity** — co-received/shipped items stored together
- **Size** — variety of location sizes
- **Characteristics** — perishable, hazmat, security, compatibility
- Same entry/exit → store close to that point | Diff entry/exit, same qty → along direct route | Diff qty → smallest r/s ratio near shipping, largest near receiving
## Warehouse Layout Model (Dedicated Storage)
### Step 1: Compute Sj and Tj for each product
- Sj = ⌈product_area / bay_area⌉ — number of bays product j needs
- Tj = total trips in + out per period for product j (if given one-way, double it)
### Step 2: Rank products by Tj/Sj decreasing
- Tj/Sj = trips per bay — highest means most traffic per bay, should be closest to docks
### Step 3: Compute dock fractions pi
- Half of all trips are inbound (receiving), half outbound (shipping)
- p_recv = (1/2) for a single receiving dock
- Split the shipping half by dock usage ratio. E.g., dock 2 used 2× dock 3: p2 = (1/2) × (2/3) = (1/3), p3 = (1/2) × (1/3) = (1/6)
- Check: all pi must sum to 1
### Step 4: Compute dik for every dock-bay pair
- dik = |xi − xk| + |yi − yk| — rectilinear distance from dock i to bay k centroid
### Step 5: Compute fk for each bay, rank increasing
- fk = Σ(pi × dik) over all docks i — weighted average distance for bay k
- Lowest fk = most accessible bay
### Step 6: Assign products to bays
- Highest Tj/Sj product gets the Sj bays with lowest fk values
- Next highest Tj/Sj product gets the next Sj lowest-fk bays
- Repeat until all products assigned
## Cube Utilization
```
Total Cube = Width × Depth × Height
Aisle Cube = Σ(aisle_w × aisle_l × height)
% Aisles   = Aisle Cube / Total Cube
```
- Honeycombing = wasted space from partial rows/stacks (vertical: below ceiling, horizontal: partial floor rows)
## Rack Types
- **Walk-through** — cross-aisle access, more light
- **Push-back** — auto-advance on retrieval, seasonal bulk
- **VNA** — <5' aisles, 40-50' height, turret trucks
- **Drive-in** — bulky/light cartons, forklift enters rack
- **Gravity flow** — rollers, easy carton transfer
- **Mobile** — 100% position util, electric, cold storage
- **Double deep** — 2 rows deep, deep-reach truck, 60-65% floor use
- **Cantilever** — long items (pipes/lumber), up to 22'
- **Carousel** — motorized rotating, 80-200 picks/hr, 1 picker only


# L09 ASRS
- Bay = vertical stack (floor→ceiling) | Row = bays side by side | Aisle = space between rows for crane
- Each crane serves BOTH sides of its aisle
- Clearances: light load (<2500 lb) = 6" gap; heavy = 9"
## Design Procedure
- Convert all dimensions to feet first (in→ft: divide by 12)
### Step 1: Loads per bay (vertical stacking)
- If height given: loads/bay = ⌊(ht − ceil − floor) / (H + gap)⌋
- If loads/bay given: height = loads/bay × (H + gap) + ceil + floor
- H = load height (ft), gap = clearance between pallets
### Step 2: Number of cranes
- cranes = ⌈throughput / (rate × avail)⌉ — or may be given directly
### Step 3: Number of rows
- Both sides of aisle (standard): rows = 2 × cranes
- One side only: rows = cranes
### Step 4: Bays per row
- bays/row = ⌈total_units / (rows × loads/bay)⌉
### Step 5: System dimensions
- **Height** = building height (from Step 1)
- **Width** = aisle_unit × cranes — aisle_unit ≥ 3 × L_load + 2' (both sides) or 2 × L_load + 2' (one side)
- **Length** = (W_load + gap) × bays/row + crane_clearance (typically 25')
- Always round UP cranes & bays/row; always round DOWN loads/bay
## Cycle Times (Bozer & White)
- S/R moves horiz & vert simultaneously → travel time = max(horiz, vert) — this is Chebyshev travel
- SC = store OR retrieve (1 trip out + back) | DC = store AND retrieve (2 trips, no return between)
### Step 1: Convert rack dimensions to feet
- L = horiz_dim × m (convert in→ft) — rack length
- H = vert_dim × n (convert in→ft) — rack height
### Step 2: Compute max travel times to farthest corner
- th = L / hv (horiz time) — where hv = horiz speed (ft/min)
- tv = H / vv (vert time) — where vv = vert speed (ft/min)
### Step 3: Compute T and Q (normalize the rack)
- T = max(th, tv) — scaling factor (longer side in time)
- Q = min(th, tv) / T — shape factor (0 < Q ≤ 1; Q=1 means square-in-time)
### Step 4: Compute expected travel times
- E(SC) = T × (1 + (Q^2)/3)
- E(DC) = T × (40 + 15(Q^2) − (Q^3)) / 30
### Step 5: Add P/D operations for full cycle times
- TP/D = time for one pick-up or deposit (given)
- SC does 2 P/D ops (pick up at P/D station + deposit at rack, or vice versa)
- DC does 4 P/D ops (deposit at rack + pick from rack + their P/D station counterparts)
- TSC = E(SC) + 2 × TP/D
- TDC = E(DC) + 4 × TP/D
