# L10 Schedule Design


### Machine Assignment Problem
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


