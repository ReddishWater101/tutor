# L10 Schedule Design
## Reject Allowance Problem
Pick lot size Q to maximize expected profit when good output x is random (one-shot job, no rerun).
- Q = lot size scheduled (decision)
- x = good units produced (random)
- p(x|Q) = prob of x good given Q (column in table)
- L = min good units customer accepts (else refused)
- U = max good units customer pays for (extras salvage)
- c = cost per unit scheduled
- s = salvage per scrap or excess good unit
- r = price per good unit sold
### Step 1: Revenue R(Q,x) piecewise on x
R = sQ                if x < L   (refused, salvage all Q)
R = rx + s(Q - x)     if L <= x <= U
R = rU + s(Q - U)     if x > U
### Step 2: Expected profit per Q (cost = cQ)
For each filled cell in column Q, compute (R - cQ) * p.
Sum the column. Pick the Q with the highest sum.
### Probability of losing money at Q*
In the column for Q*, find cells where profit is negative.
Sum those cells' probabilities. That sum = P(loss).

## Machine Assignment Problem
Identify variables a, b, t for one machine operation cycle:
- a = coupled time (operator + machine on THE SAME task)
- b = operator-only time (machine not needed for this task)
- t = machine-only time (operator not needed for this task)
- Co = cost per operator per hour ($/hr)
- Cm = cost per machine per hour ($/hr)
- m = number of machines assigned to one operator
- n' = ideal number of machines per operator
- TC(m) = total cost per unit produced when assigning m machines
### Step 1: Ideal assignment (n=#machines)
n' = (a + t) / (a + b)
### Step 2: Get integer candidates to compare
n1 = floor(n'), n2 = ceil(n')
### Step 3: Cost per unit for each candidate
TC(m) = (Co + m*Cm)(a+t)/m   if m <= n'
TC(m) = (Co + m*Cm)(a+b)     if m > n'
Pick m with lowest TC. Units dont matter as long as uniform.

# L11 Break Even Analysis
## Investment Evaluation (ROI / PBP / NPV)
Evaluate a capital investment over N years vs the existing or alternative cashflow.
- C = initial cost of investment (paid year 0)
- S = salvage value at end of year N
- N = planning horizon (years)
- i = discount rate (given: bond rate, required return, WACC)
- CF_old(t) = cashflow without investment, year t
- CF_new(t) = cashflow with investment, year t
- G(t) = gain from investment in year t
### Step 1: Build the gain column G(t)
G(t) = CF_new(t) - CF_old(t)
If problem says investment boosts cashflow by r%:
G(t) = r * CF_old(t)
This G(t) column feeds Steps 2-4.
### Step 2: ROI (return on investment)
TG = sum of G(t) for t = 1..N
ROI = (TG + S - C) / C
### Step 3: PBP (payback period)
Subtract G(t) from C cumulatively until C is recovered.
Let k = last full year still short, R = leftover unpaid.
PBP=k+(R/G(k+1))
Salvage NOT counted unless told otherwise.
### Step 4: NPV (net present value)
PV(t) = G(t) / (1 + i)^t       for t = 1..N
For year N add salvage:
PV(N) = (G(N) + S) / (1 + i)^N
TPV = sum of PV(t)
NPV = TPV - C
NPV > 0 means it beats the discount rate.

# L12-A Minisum
## Minisum Facility Location
Place new facility to minimize total weighted rectilinear distance to existing sites.
- (x_i, y_i) = location of existing facility i (given)
- w_i = weight of facility i (given: trips, time, volume)
- (x*, y*) = new facility location (find this)
- z* = total weighted distance at optimum
- Rectilinear dist from new to i: |x* - x_i| + |y* - y_i|
### Step 1: Find x* (weighted median of x-coords)
Rectilinear distance lets you solve x and y independently.
1. Sort all facilities by x-coordinate (ascending)
2. List each weight w_i in that sorted order
3. Cumulate weights top to bottom
4. W = total weight; find first row where cumulative >= W/2
5. x* = that row's x-coordinate
If cumulative hits exactly W/2, any x between that row's
and the next row's x-coordinate is optimal.
### Step 2: Find y* (weighted median of y-coords)
Repeat Step 1 sorting by y-coordinate instead.
### Step 3: Objective value z*
z* = sum of w_i * (|x* - x_i| + |y* - y_i|) for all i
Compute each facility's weighted distance, then sum.

# L12-B Minimax
## Minimax Facility Location
Place new facility to minimize the maximum rectilinear distance to any existing facility.
- (x_i, y_i) = location of existing facility i (given)
- (x*, y*) = new facility location (find this)
- z* = minimax distance (smallest possible worst-case)
- No weights in this problem
### Step 1: Transform coordinates
u_i = x_i + y_i,  v_i = x_i - y_i   for each facility
This converts rectilinear distance into max(|u - u_i|, |v - v_i|).
### Step 2: Ranges and half-ranges
u_max, u_min = largest and smallest u_i
v_max, v_min = largest and smallest v_i
R_u = (u_max - u_min) / 2
R_v = (v_max - v_min) / 2
### Step 3: Minimax distance
z* = max(R_u, R_v)
### Step 4: Optimal line segment in (u,v)
u_mid = (u_max + u_min) / 2
v_mid = (v_max + v_min) / 2
If R_u > R_v: u* = u_mid, v* in [v_mid-(R_u-R_v), v_mid+(R_u-R_v)]
If R_v > R_u: v* = v_mid, u* in [u_mid-(R_v-R_u), u_mid+(R_v-R_u)]
If R_u = R_v: single optimal point (u_mid, v_mid)
### Step 5: Convert back to (x,y)
x = (u + v) / 2,  y = (u - v) / 2
Plug endpoints of the (u,v) segment to get (x,y) endpoints.


# L13 Project Management
## Critical Path Method (CPM)
Find the critical path and earliest/latest times from a precedence table.
- ES = early start, EF = early finish of an activity
- LS = late start, LF = late finish of an activity
- Slack = how much an activity can delay without delaying the project
- Predecessors = activities that must finish before this one starts
- Successors = activities that cannot start until this one finishes
### Step 1: Forward pass (left to right)
Process activities so all predecessors are computed first.
ES = 0                             if no predecessors
ES = max(EF of all predecessors)   if has predecessors
EF = ES + duration
The largest EF across all activities = project duration T.
### Step 2: Backward pass (right to left)
Process activities so all successors are computed first.
LF = T                             if no successors
LF = min(LS of all successors)     if has successors
LS = LF - duration
### Step 3: Slack
Slack = LS - ES   (equivalently LF - EF)
### Step 4: Critical path
All activities with Slack = 0 form the critical path.
It is the longest path through the network; its length = T.

# L14 Ergonomic Considerations
## Ergonomic Risk Factors
Identify hazards in a workplace task and propose design fixes.
Common risk factors (match whichever apply to the scenario):
- Forceful exertion: heavy lifting, pushing, pulling, gripping
  Fixes: mechanical assists (lifts, dollies, conveyors), reduce load size
- Awkward posture: bending, twisting, reaching overhead or below knees
  Fixes: adjustable work height, bring work to waist level
- Repetitive motion: same movement cycle repeated frequently
  Fixes: job rotation, automate the repetitive task
- Contact stress: body pressing against hard edges or surfaces
  Fixes: padded handles/edges, anti-fatigue mats
- Static posture: holding one position for extended time
  Fixes: sit-stand workstations, scheduled rest/stretch breaks
- Vibration: prolonged use of vibrating tools or vehicles
  Fixes: vibration-dampened tools/seats, limit exposure time
