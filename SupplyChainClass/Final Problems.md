# deterministic inventory
## 1. Manufacturer EPQ | Source: Assignments/Homework_1_solution.pdf, Pages 3-4
Consider a manufacturer that sells a product for which the annual demand is relatively stable and is 12,000 units per year. The production setup cost for this product is $500 per setup, and the annual inventory holding cost is $50 per unit per year. Suppose that the production rate is 20,000 units per year.

a. What is the optimal order quantity for this operational setting?

b. How many production setups would have to be made if the optimal order quantity you determined in part (a) is used for this operational setting?

c. What is the average annual total cost of production setup and inventory holding if the optimal order quantity you determined in part (a) is used for this operational setting?

d. Currently, when the production line is setup 1,000 units are produced per production setup. What is current average annual total cost of production setup and inventory holding for this operational setting?

e. Everything else being equal, what should the production rate should be for 1,000 units to be the optimal order quantity for this system?

*I did this problem first try no problems*


# deterministic inventory
## 2. Two Suppliers: All-Units vs. Incremental Discount | Source: Assignments/ProblemSet_1_EOQ.pdf, Pages 5-6
Consider a scenario with two different suppliers offering different discount schemes. Supplier A offers an all-unit discount scheme with a unit price of $10.00 for quantities up to (but excluding) 5,000 and $9.00 if the quantity is 5,000 or higher. Supplier B offers an incremental discount scheme with a unit price of $12.00 for quantities up to 1,000, unit price of $10.00 for any quantity between 1,000 and 3,000, and unit price of $7.50 for any quantity 3,000 or higher.

The product's demand is 1,000 units/week. The cost of ordering from either supplier is $1,000 and an annual inventory carrying rate of 25 percent is used by the company. The company operates for 52 weeks a year.

a. What are the possible candidate quantities for supplier A's all-unit discount scheme?

b. What are the possible candidate quantities for supplier B's incremental discount scheme?

c. Which inventory policy is optimal? Your answer should include the choice of supplier and the optimal quantity to order.

*know that the breakpoints always start with b0 = 0 units, while price starts at c0. c0 is the price in the range b0 to b1.   additionally, know that when you are solving for the incremental discount scheme, if you are going through step 3 and dont have a bj+1, you just go with the qj value as the candidate.*

# stochastic inventory
## 3. Happy Henry's Car Dealer Multi-Case Newsvendor | Source: Assignments/ProblemSet_2_Newsvendor.pdf, Pages 7-8
Happy Henry's car dealer sells an imported car called the EX123. Once every three months, a shipment of the cars is made to Happy Henry's. Emergency shipments can be made between these three-month intervals to resupply the cars when inventory falls short of demand. The emergency shipments require two weeks, and buyers are willing to wait this long for the cars, but will generally go elsewhere before the next three-month shipment is due. From experience, it appears that the demand for the EX123 over a three-month interval is normally distributed with a mean of 60 and a variance of 36. The cost of holding an EX123 for one year is $500. Emergency shipments cost $250 per car over and above normal shipping costs.

a. How many cars should Happy Henry's be purchasing every three months?

b. Repeat the calculations, assuming that excess demands are backordered from one three-month period to the next. Assume a loss-of-goodwill cost of $100 for customers having to wait until the next three-month period and a cost of $50 per customer for bookkeeping expenses.

c. Repeat the calculations, assuming that when Happy Henry's is out of stock of EX123s, the customer will purchase the car elsewhere. In this case, assume that the cars cost Henry an average of $10,000 and sell for an average of $13,500. Ignore loss-goodwill costs for this calculation.



# stochastic inventory
## 4. Santori Bags (Q,R) Policy and Service Levels | Source: Assignments/ProblemSet_3_qrpolicy.pdf, Pages 4-6
Santori Bags sells a variety of briefcases and handbags. The bags are shipped from a manufacturer in Italy. During an interview, Marilyn Santori, the owner of the business, says that "In order to make sure that I never run out of stock, I try to keep at least three months' supply in stock. When the inventory drops to that level, I order another three months' supply. I have been using this method for the past sixteen years and it has worked for my company." Genuine leather bags cost the company $55 and are sold for $150 each. The cost of placing an order with the Italian manufacturer and receiving the bags is $750, and it takes five weeks to receive the shipment from Italy. The weekly demand is approximately normally distributed with a mean of 70 bags and a standard deviation of 20 bags. Marilyn's investments in the money market bring in approximately 12 percent earnings, and the insurance and tax related expenses amount to approximately 8 percent of the value of the goods in inventory.

a. What are the reorder level and order quantity for the bags that Marilyn is currently using?

b. What Type 2 service level is being achieved with the current policy?

c. What would the reorder level and order quantity be, if Marilyn were to use a Type 1 service level of 98 percent?

d. Suppose that the excess demand is back-ordered, and Marilyn offers a 10 percent discount in price to her customers when a customer order has to be back-ordered. In this case, determine the optimal values of the reorder level and order quantity.



# transportation
## 5. WeMove vs. Fast Horses 3PL Carrier Selection | Source: Assignments/Homework_5_Questions.pdf, Page 1
WeMove Inc. is a shipping company that provides 3PL service for BWAH Corp. WeMove makes deliveries from BWAH's manufacturing plant to its central warehouse. Based on WeMove's past performance, the transportation lead time for deliveries can assumed to be normally distributed with a mean of 5 days and a standard deviation of 2 days. Currently, WeMove charges BWAH $0.50/unit for shipping costs. The following information is also available.

Average demand at the warehouse: 150 units/day.
Standard deviation of demand at the warehouse: 20 units/day.
Fixed ordering cost: $250/order.
Unit cost: $40/unit.
Shipping quantity: as per EOQ.
In-transit inventory carrying rate: 15% per year.
On-site inventory carrying rate: 20% per year.
Probability of not stocking out during lead time: 90%.
Operating days at the warehouse: 360 days/year.
Out-of-stock costs for the warehouse: unknown.

a. What are the parameters of demand during lead time?

b. What is the total annual logistics cost (including on-site inventory, ordering, transportation and in-transit inventory holding) associated with the current system?

c. Another company Fast Horses, Inc. has made an offer to BWAH so that the guaranteed transportation lead time with a mean of 4 days and a standard deviation of 1 day, the distribution for which can assumed to be approximately normally distributed. Fast Horses would charge BWAH $1.00/unit for shipping costs. Should BWAH accept this new offer?
