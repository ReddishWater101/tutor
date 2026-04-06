# The QR Policy Explained Like a Human

## What Even Is the QR Policy

Okay so the whole idea behind the q r policy is pretty simple once you step back from the math. You are a business that sells some product on an ongoing basis. Unlike the newsvendor where you order once and whatever is left over is trash, here unsold stuff carries over to the next period. You keep selling it week after week or month after month. The question is just: when should I place an order, and how much should I order each time?

The answer the q r policy gives you is two numbers. The first is q, which is your order quantity, meaning every time you place an order you order exactly q units. The second is r, which is your reorder level, meaning you watch your inventory and the moment it drops to r units, you pick up the phone and place that order for q units. That is it. That is the whole policy. Watch your inventory, and when it hits r, order q.

## Why Do We Need Lead Time Math

Here is the thing that makes this tricky. When you place an order, it does not show up instantly. There is a lead time, meaning a gap between when you order and when the stuff actually arrives. During that lead time you are still selling product and your inventory keeps dropping. So the real question behind choosing r is: how much inventory do I need to have on hand when I place the order so that I do not run out before the shipment arrives?

That is why the very first step in every single one of these problems is figuring out the demand during lead time. If your lead time is 3 months and you sell on average 400 units per month, then the average demand during lead time is just 3 times 400 which is 1200. The standard deviation scales a little differently because of how statistics works. You take the monthly standard deviation and multiply it by the square root of the lead time. So if the monthly standard deviation is 48 and lead time is 3 months, the standard deviation of demand during lead time is 48 times the square root of 3. That gives you roughly 83.14. The reason for the square root is that variances add when you combine independent periods, and standard deviation is the square root of variance. So you are really adding 3 variances and then taking the square root of the total.

Now you have a normal distribution for demand during lead time, with its own mean and standard deviation. This is the foundation for everything else.

## Full Backlogging vs Lost Sales and Why It Matters

Before you do any calculations you need to know one thing about your customers. When you run out of stock, what happens? There are two possibilities.

Full backlogging means your customers are patient. They say okay I will wait, and when your shipment arrives you fill their order. You do not lose the sale, but you do upset them a bit, so there is a goodwill cost. In this case the cost of understocking is just the goodwill cost b, because you still eventually make the sale. And the cost of overstocking is just the holding cost h, because extra units just sit in inventory costing you money. So c sub u equals b and c sub o equals h.

Lost sales means your customers leave and buy from a competitor. You lose the sale entirely. In this case the cost of understocking is much bigger because you lose the profit margin plus the goodwill. So c sub u equals p minus c plus b, where p is the selling price, c is the purchase cost, and b is the goodwill cost. The cost of overstocking is still h.

This distinction is critical because it completely changes the critical ratio, which changes everything downstream.

## The Critical Ratio and What It Means

The critical ratio is c sub u divided by the quantity c sub u plus c sub o. This is the same idea as the newsvendor. It tells you the probability of demand being less than or equal to your stocking level that would be optimal. A high critical ratio means understocking is way more expensive than overstocking, so you should stock more. A low critical ratio means overstocking is relatively painful, so you should be more conservative.

You take this critical ratio, go to your standard normal z table, and find the z value that corresponds to that probability. This z value tells you how many standard deviations above or below the mean your reorder level should be.

## The Iterative Procedure Step By Step

Here is where people get confused, but it is actually not that bad once you see the logic. The problem is that q and r depend on each other. Your optimal order quantity q depends on how much shortage you expect, which depends on r. But r depends on q through the formulas. So you cannot solve for one without knowing the other. The solution is to iterate back and forth until the numbers stabilize.

Step one is you start with a simple estimate of q using the EOQ formula. EOQ stands for economic order quantity and it is just the square root of 2 times the annual demand times the fixed ordering cost, divided by the annual holding cost per unit. This gives you a ballpark order quantity ignoring shortages entirely.

Step two is you use that q to find a z value using a formula that involves the critical ratio and q. Specifically you find z such that the complementary loss function of z equals q times c sub o divided by the quantity c sub u times sigma sub L, where sigma sub L is the standard deviation of demand during lead time. Wait let me back up. For the first iteration with full backlogging, you find z by solving for the probability that a standard normal exceeds z equals q times h divided by the quantity b times sigma sub L. Actually the exact formula depends on the specific model. Let me just explain the intuition.

What you are really doing is finding the z value from the critical ratio. You compute the critical ratio, which is c sub u over c sub u plus c sub o, and then find the z value from the standard normal table where the cumulative probability equals that critical ratio. Then your reorder level r equals the mean demand during lead time plus z times the standard deviation of demand during lead time. That is it. The reorder level is just the average demand during lead time plus some safety buffer. The z value controls how big that safety buffer is.

Step three is you recompute q using a more refined formula that accounts for expected shortages. The updated q formula is the square root of 2 times annual demand times the quantity K plus c sub u times n of r, all divided by h. Here K is the fixed ordering cost, c sub u is the underage cost, and n of r is the expected number of units short per cycle. This n of r value comes from something called the standard loss function, often written as L of z. You look up L of z in the table and then n of r equals sigma sub L times L of z.

Step four is you take that new q and go back to step two and recompute r. You keep going back and forth until q and r stop changing. For homework and exam purposes they usually tell you to stop after one iteration, which is a relief.

## What the Reorder Level Actually Means

The reorder level r has two pieces. The first piece is the mean demand during lead time, which is just the average amount you expect to sell while waiting for your order. The second piece is the safety stock, which is z times sigma sub L. Safety stock is extra inventory you hold as a buffer against the randomness of demand. If demand were perfectly predictable you would not need any safety stock and r would just equal the mean. But demand is random so you pad it.

The expected safety stock level is z times sigma sub L. That is it. That is all safety stock is. It is the buffer above average demand during lead time.

## The Total Annual Cost

The total annual cost has three components. First is the annual ordering cost, which is the number of orders per year times the fixed cost per order. The number of orders per year is annual demand divided by q, so this piece is D over q times K. Second is the annual holding cost, which accounts for holding both your cycle stock and your safety stock. The formula is h times the quantity q over 2 plus r minus the mean demand during lead time. The q over 2 part is the average cycle stock and r minus mu sub L is the safety stock. Third is the annual shortage cost, which is the annual demand over q times c sub u times n of r. This is how much you pay for stockouts per year. You add all three together and that is your total cost. Sometimes they tell you to ignore the purchasing cost component, which would be c times D, because they did not give you the unit purchase cost.

## Service Levels Instead of Shortage Costs

Sometimes instead of giving you a goodwill cost, they tell you to target a specific service level. There are two types and they mean very different things.

Type I service level is the probability of not stocking out during a lead time period. It is also called the cycle service level. If someone says I want a 98 percent Type I service level, they mean that 98 percent of the time I place an order I want to not run out before the shipment arrives. To find the reorder level for a Type I service level, you just find the z value where the cumulative standard normal probability equals your target. So for 98 percent you look up 0.98 in the z table and get z equals about 2.05. Then r equals mu sub L plus z times sigma sub L. For the order quantity, you just use the basic EOQ formula since there is no shortage cost to factor in. That is the nice thing about Type I, it is very straightforward.

Type II service level is the fill rate, meaning the fraction of demand that is filled from stock immediately without backordering. This is usually what customers actually care about more, because it measures how much of total demand gets satisfied right away. A 98 percent Type II service level means 98 percent of all units demanded are filled immediately from on-hand inventory.

For Type II, the formula connects the order quantity q to the expected shortage per cycle. Specifically, n of r equals q times the quantity 1 minus beta, where beta is your target fill rate. So if beta is 0.98 and q is 2000, then n of r equals 2000 times 0.02 which is 40. Then you work backwards. You know n of r equals sigma sub L times L of z, so L of z equals n of r divided by sigma sub L. You look up that L of z value in the loss function table to find z, and then compute r from z.

## System Assessment, Working Backwards

Sometimes the problem goes the other direction. Instead of saying design me a policy, they say here is a policy that is already running, tell me how well it is doing. They give you q and r and ask you to find the service levels.

For Type I, you take the given r, subtract the mean demand during lead time, and divide by sigma sub L. That gives you z. Then you look up z in the standard normal table to find the cumulative probability and that probability is your Type I service level.

For Type II, you use that same z to look up L of z in the loss function table. Then n of r equals sigma sub L times L of z. Then beta equals 1 minus n of r divided by q. That is your Type II service level.

## The Loss Function and Why It Matters

The standard loss function L of z shows up everywhere in these problems and it is worth understanding what it represents. L of z is the expected number of standard deviations of shortage, given a z value safety factor. When z is high, meaning you have a lot of safety stock, L of z is very small because you rarely run out. When z is low or negative, L of z is large because shortages are common. You always look this up in a table, you never calculate it by hand. Just know that n of r, the expected shortage per cycle in actual units, equals sigma sub L times L of z.

## Quick Mental Checklist for Exam Problems

When you see a q r problem, here is how to orient yourself fast. First, figure out the time units. Is demand given weekly or monthly. Is lead time in the same units. Convert if needed. Second, compute mean and standard deviation of demand during lead time. Mean is lead time times average demand per period. Standard deviation is standard deviation per period times square root of lead time. Third, figure out if it is full backlogging or lost sales based on what customers do when you are out of stock. This tells you c sub u and c sub o. Fourth, check what they are asking. If they give you a shortage cost, you are doing the iterative optimization. If they give you a target service level, you are doing system design. If they give you q and r and ask what service level you are achieving, you are doing system assessment.

The formulas are all connected by the same core ideas. The critical ratio balances overstocking versus understocking. The z value translates that ratio into a position on the normal distribution. The reorder level is just the mean demand during lead time plus a safety buffer. And the loss function tells you how much shortage to expect for any given safety buffer. Everything else is just plugging numbers into those relationships.

You have got this. Take a breath, read the problem carefully, figure out which scenario you are in, and the steps will follow.
