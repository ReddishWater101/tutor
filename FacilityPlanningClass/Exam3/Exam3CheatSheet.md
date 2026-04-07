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


# L12-A Minisum


# L12-B Minimax


# L13 Project Management


