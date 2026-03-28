Everything You Need to Know for Exam 2


PART ONE -- THE NEWSVENDOR MODEL

Alright, so picture this. You run a business and you have to decide how much to order before you actually know how many people are going to show up and buy. Think of a newspaper stand, a popcorn booth, or a seasonal holiday store. You order before the season, and then you just hope you guessed right.

If you order too much, you are stuck with leftovers and you lose money. If you order too little, customers walk away and you miss out on profit. The Newsvendor model is the math that finds the best middle ground.

The whole thing boils down to two costs. The overage cost, called c sub o, is what each leftover unit costs you. The underage cost, called c sub u, is what each unit of missed demand costs you. You want to balance these two against each other.


The Critical Ratio

Here is the punchline. You compute a number called the critical ratio, and it tells you exactly where to set your order quantity. The critical ratio equals c sub u divided by the sum of c sub u plus c sub o. You then set F of q star equal to this ratio, where F is the cumulative distribution function of demand.

If the critical ratio is high, say 0.90, it means underage is way more expensive than overage, so you should stock a lot. If the critical ratio is low, say 0.30, overage is the bigger deal, so you stock conservatively.

To actually find q star, you look up the critical ratio in the z table if demand is normally distributed. Find the z value where F of z equals the critical ratio, then compute q star equals mu plus z star times sigma.

If demand is discrete, you just scan down the cumulative probability column and pick the first value that meets or exceeds the critical ratio.


Cost Minimization versus Profit Maximization

Sometimes the problem gives you c sub u and c sub o directly. Other times it gives you business parameters like selling price p, purchase cost c, salvage value v, and goodwill cost b. These are just two ways of saying the same thing.

The connection is simple. The underage cost c sub u equals p minus c plus b. That is, the profit margin you miss out on plus the goodwill penalty. The overage cost c sub o equals c minus v. That is, how much you lose per unsold unit after salvage.

Either way, the critical ratio formula gives you the same answer.


Multiple Periods

What if leftovers do not spoil and can be sold next period? Now you are in a multi period Newsvendor. The key question becomes: what happens when you run out?

Under full backlogging, customers wait. You eventually fill their order next period. In this case the critical ratio simplifies to b divided by b plus h, where h is the holding cost per unit per period. Notice that the selling price and purchase cost drop out entirely. Over the long run every unit gets sold eventually, so only the holding and backlogging costs matter for deciding how much to stock.

Under lost sales, customers leave and buy from someone else. Now the critical ratio is p plus b minus c, divided by p plus b minus c plus h. The selling price and cost stay in the formula because lost demand means permanently lost revenue.

The takeaway: you always stock more under lost sales than under full backlogging, because running out is more painful when customers leave forever.


PART TWO -- THE Q R POLICY

The Newsvendor assumes zero lead time and no fixed ordering cost. In the real world, deliveries take time and every order has a setup cost. The q comma r policy handles this.

The idea is straightforward. You watch your inventory continuously. When it drops to a level r, called the reorder point, you place an order for q units. After a lead time of tau periods, the order shows up.


Demand During Lead Time

Since demand keeps happening while you wait for your order, you need to figure out the distribution of demand during lead time, or D D L T.

If the lead time is a constant tau periods, and demand per period has mean mu sub D and standard deviation sigma sub D, then the mean of D D L T is tau times mu sub D, and the standard deviation of D D L T is the square root of tau, times sigma sub D.

This is always the first step in any q r problem. Get the D D L T parameters before anything else.


Safety Stock

Safety stock is the expected inventory on hand when your order arrives. Under full backlogging, it is simply s equals r minus mu sub L. Under lost sales, it is s equals r minus mu sub L plus n of r. The n of r term shows up because under lost sales, excess demand disappears instead of eating into your inventory, so you tend to have more on hand when the order arrives.


The Two Equations and the Iterative Approach

Taking derivatives of the cost function gives you two equations that depend on each other.

Equation one gives you q: q star equals the square root of 2 lambda times the quantity K plus b times n of r, divided by h.

Equation two gives you r. Under full backlogging: 1 minus F of r equals q h divided by b lambda. Under lost sales: 1 minus F of r equals q h divided by the quantity b lambda plus q h.

Since q depends on r and r depends on q, you solve them iteratively.

Start by setting q equal to the basic E O Q, which is the square root of 2 K lambda over h. Plug that q into equation two to get r. Use r to compute n of r through the loss function. Plug n of r back into equation one to get a new q. Repeat until nothing changes. This usually takes just one or two rounds.

When working with the z table, here is the flow. From equation two you get F of r. Look up the z value where F of z matches. Then read off L of z from the loss function column. Compute n of r as sigma sub L times L of z. Interpolate when needed, and round z to two decimals and L of z to three decimals.

At the end, r star equals mu sub L plus z star times sigma sub L.


SERVICE LEVELS

Sometimes you cannot estimate the backlogging cost b. Instead you specify a service level, which is a target for how available the product should be.

Type One service level, also called cycle service level, is the probability of not stocking out during any given lead time. If you want alpha equals 0.99, you set F of r equals 0.99, look up the z value, and compute r. The order quantity is just the basic E O Q. Q and r are determined independently here.

Type Two service level, also called fill rate, is the fraction of total demand met directly from stock. If you want beta equals 0.99, you compute n of r equals 1 minus beta times q, where q is the basic E O Q. Then work backward through the loss function to find z and then r.

The key difference: for the same percentage, Type One is stricter. It requires a higher reorder point. Type One says every single cycle must avoid stockouts 99 percent of the time. Type Two says 99 percent of all units demanded should be filled from stock, which is more forgiving because small stockouts in a large order quantity barely dent the fill rate.


Assessing an Existing Policy

If the exam gives you q and r and asks for the implied service level, work backward.

For Type One: compute z equals r minus mu sub L divided by sigma sub L. Look up F of z. That is your alpha.

For Type Two: compute z the same way. Look up L of z. Compute n of r equals sigma sub L times L of z. Then beta equals 1 minus n of r divided by q.


Quick Reference

Newsvendor single period: F of q star equals c sub u over c sub u plus c sub o

Profit max version: c sub u equals p minus c plus b, c sub o equals c minus v

Multi period full backlogging: F of q star equals b over b plus h

Multi period lost sales: F of q star equals p plus b minus c over p plus b minus c plus h

Q R full backlogging reorder equation: 1 minus F of r equals q h over b lambda

Q R lost sales reorder equation: 1 minus F of r equals q h over b lambda plus q h

Q R order quantity: q equals the square root of 2 lambda times K plus b n of r over h

Safety stock full backlogging: s equals r minus mu sub L

Safety stock lost sales: s equals r minus mu sub L plus n of r

D D L T constant lead time: mu sub L equals tau mu sub D, sigma sub L equals square root of tau times sigma sub D

n of r equals sigma sub L times L of z

r equals mu sub L plus z times sigma sub L

Type One: F of r equals alpha, q equals E O Q

Type Two approximate: n of r equals 1 minus beta times q, q equals E O Q
