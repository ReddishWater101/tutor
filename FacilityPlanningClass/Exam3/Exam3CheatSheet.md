# L10 Schedule Design
## Scrap Estimates (Series Yield)
Find initial input I1 so that n operations in series still deliver O_n good units after scrap at each step.
- n = number of operations in series (machine 1 -> 2 -> ... -> n)
- P_k = scrap rate at machine k (fraction defective)
- y_k = 1 - P_k = yield at machine k (fraction passing)
- O_n = required good output (customer demand)
- I1 = initial input to machine 1 (find this)
- Q_k = quantity entering machine k (feeds Machine Fractions)
### Step 1: Get each yield y_k
If the problem gives scrap rate P_k, set y_k = 1 - P_k.
If the problem already gives a yield number (e.g., 0.95), use it directly as y_k.
### Step 2: Handle any fallback path
If failures at machine k are rerouted to a backup with yield y_b:
y_k_eff = y_k + (1 - y_k) * y_b
Replace y_k with y_k_eff for the rest of the problem.
### Step 3: Compute the initial input I1
I1 = O_n / (y_1 * y_2 * ... * y_n)
Round up to the next whole unit. That is the material to start.
### Step 4: Compute Q_k entering each machine
Q_k = O_n / (y_k * y_(k+1) * ... * y_n)
So Q_1 = I1 and Q_n = O_n / y_n. Carry these Q_k into Machine Fractions.

## Machine Fractions
Compute the number of machines F_k of each type needed to meet demand.
- k = machine index (A, B, ...)
- Q_k = quantity entering machine k (from Scrap Step 4)
- S_k = standard time per unit on machine k
- H_k = total hours available per period on machine k
- E_k = historical efficiency (actual rate / std rate)
- R_k = availability / reliability (fraction of H_k up)
- F_k = number of machines of type k needed
### Step 1: Gather inputs and match units
Pull Q_k from Scrap Step 4; S_k, H_k, E_k, R_k from the problem table.
Convert every percentage to a decimal (85% -> 0.85).
Make S_k and H_k share a time unit (both hr or both min).
### Step 2: Apply the formula
F_k = (Q_k * S_k) / (H_k * E_k * R_k)
Put EVERY given % multiplier (availability fraction, efficiency, reliability, ...) into the denominator as a product. If one of them is not given, just drop it.
### Step 3: Round up to integer machines
Number of machines of type k = ceil(F_k).
### Step 4: Multi-visit routes (e.g., A -> B -> A)
If a part visits machine k more than once, compute (Q * S) / (H_k * E * R) for EACH visit using that visit's own Q, S, E, R. Sum the visits, THEN round up.

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
### Idle time rule
m < n' : machine idle = 0; operator idle = Tc - m(a+b)
m > n' : operator idle = 0; machine idle = Tc - (a+t)
m = n' : both zero (perfect balance).
Operator has no idle whenever m >= n'.

# L11 Break Even Analysis
## Definitions
- Fixed cost: unchanged by volume (rent, machine purchase)
- Variable cost: scales with volume (materials, utilities, shipping)
- Planning horizon: width of the window for evaluating each investment alternative
- Discount rate i: interest rate, required rate of return, or WACC
- Crossover / break-even: volume at which two total-cost curves meet

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
## Definitions
Minisum = minimize weighted sum of absolute distances. Optimum is the weighted MEDIAN on each axis (minimizing squared distances would give the mean). Use when weights matter: trips, cost, flow, demand probability.

## Minisum Facility Location
Place new facility to minimize total weighted rectilinear distance to existing sites.
- (a_i, b_i) = location of existing facility i (given)
- w_i = weight of facility i (trips, time, volume)
- (x*, y*) = new facility location (find this)
- z* = total weighted distance at optimum
- W = sum of all w_i
### Step 1: Find x* (cumulative weight algorithm)
Sort facilities by a_i (x-coord) in ascending order.
List w_i in that sorted order, cumulate top to bottom.
x* = a_i of the first row where cumulative >= W/2.
If cumulative hits exactly W/2, any x between that row's a_i
and the next row's a_i is also optimal.
### Step 2: Find y* (same algorithm on y)
Sort facilities by b_i (y-coord) in ascending order.
List w_i in that order, cumulate, find first row >= W/2.
y* = b_i of that row.
### Step 3: Objective value z*
z* = sum of w_i * (|x* - a_i| + |y* - b_i|) for all i
Compute each facility's weighted distance, then sum.

# L12-B Minimax
## Definitions
Minimax = minimize the worst-case (furthest) distance. No weights. Use when the farthest facility is what matters: emergency services, restrooms, cafeterias. Relaxing z above z* expands the optimum from the A-B segment into a diamond (square) contour; any point inside is optimal at that z.

## Minimax Facility Location
Place new facility to minimize the maximum rectilinear distance to any existing facility.
- (a_i, b_i) = location of existing facility i (given)
- (x*, y*) = new facility location (often a line segment, not a point)
- z* = minimax distance (smallest possible worst case)
- No weights in this problem
### Step 1: Compute four corner constants
c1 = min(a_1+b_1, ..., a_i+b_i)
c2 = max(a_1+b_1, ..., a_i+b_i)
c3 = min(-a_1+b_1, ..., -a_i+b_i)
c4 = max(-a_1+b_1, ..., -a_i+b_i)
### Step 2: Compute c5
c5 = max(c2 - c1, c4 - c3)
### Step 3: Maximum distance z*
z* = c5 / 2
### Step 4: Optimal line segment endpoints
A = ((c1 - c3)/2, (c1 + c3 + c5)/2)
B = ((c2 - c4)/2, (c2 + c4 - c5)/2)
The optimal new facility is anywhere on the segment from A to B.
If A = B, the optimum is a single point.

# L13 Project Management
## Definitions
- Project: temporary endeavor for a unique deliverable
- 5 sub-processes: Initiate, Plan, Execute, Control, Close (Refining is NOT one)
- Triple constraint: Time, Budget, Scope
- WBS: Work Breakdown Structure (deliverable tree)
- Dummy activity: zero-duration dashed arc used to enforce correct precedence while keeping each activity uniquely named
- Gantt chart: time bars; simple but hides task dependencies
- CPM gives the critical path; PERT adds statistical time estimates
- Critical path: longest path; any delay on it delays the project

## Critical Path Method (CPM)
Find earliest/latest times and the critical path from a precedence table.
- ES = early start, EF = early finish of an activity
- LS = late start, LF = late finish of an activity
- Slack = how much an activity can delay without delaying the project
- Predecessors = activities that must finish before this one starts
- Successors = activities that cannot start until this one finishes
- T = total project duration
On your diagram, label each activity with ET(ES, EF) above
and LT(LS, LF) below as you work through the steps.
### Step 1: Forward pass (left to right)
Process activities so all predecessors are computed first.
ES = 0                             if no predecessors
ES = max(EF of all predecessors)   otherwise
EF = ES + duration
Write ET(ES, EF) on each activity. T = max(EF) = project duration.
### Step 2: Backward pass (right to left)
Process activities so all successors are computed first.
LF = T                             if no successors
LF = min(LS of all successors)     otherwise
LS = LF - duration
Write LT(LS, LF) on each activity.
### Step 3: Slack and critical path
Slack = LS - ES   (equivalently LF - EF)
Critical path = all activities with Slack = 0 (i.e., ET = LT).
It is the longest path through the network; its length = T.

# L14 Ergonomic Considerations
## Pillars of Health & Safety (AREC)
- Anticipate: foresee hazards before they arise
- Recognize: identify hazards present on the job
- Evaluate: assess risk level and severity
- Control: eliminate, engineer out, admin, or PPE

## Ergonomic Risk Factors
Identify hazards in a workplace task, then propose two design fixes per hazard.
Match whichever risk factors apply to the scenario:
- Forceful exertion: heavy lifting, pushing, pulling, gripping
  Fixes: mechanical assists (lifts, dollies, conveyors); reduce load size
- Awkward posture: bending, twisting, reaching overhead or below knees
  Fixes: adjustable work height; bring work to waist level
- Repetitive motion: same cycle repeated frequently
  Fixes: job rotation; automate the repetitive task
- Contact stress: body pressing against hard edges or surfaces
  Fixes: padded handles/edges; anti-fatigue mats
- Static posture: holding one position for extended time
  Fixes: sit-stand workstations; scheduled rest/stretch breaks
- Vibration: prolonged use of vibrating tools or vehicles
  Fixes: vibration-dampened tools/seats; limit exposure time
