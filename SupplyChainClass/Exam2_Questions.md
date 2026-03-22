# Exam 2 - All Questions (Lectures 4-7 & Problem Set 2)

## Lecture 4: Inventory - Newsvendor

1. **Billy's Bagels** — Billy's Bagels bakes fresh bagels each morning. The daily demand for bagels can be characterized using a discrete random variable for which an empirical distribution can be obtained using historical sales data:

| Dozens of Bagels Sold | Probability | Cumulative Probability |
|---|---|---|
| 0 | 0.05 | 0.05 |
| 5 | 0.10 | 0.15 |
| 10 | 0.10 | 0.25 |
| 15 | 0.20 | 0.45 |
| 20 | 0.25 | 0.70 |
| 25 | 0.15 | 0.85 |
| 30 | 0.10 | 0.95 |
| 35 | 0.05 | 1.00 |

The bagels cost 8 cents/unit to bake and are sold for 35 cents/unit. Bagels unsold at the end of the day are purchased by a nearby charity soup kitchen for 3 cents/unit. How many dozens of bagels should Billy's bake each day?

*(Lecture 4, Slides 20-22)*

2. **St. Valentine's Cards** — A drugstore in Coral Springs, Florida sells St. Valentine's Day cards. The store manager has the following empirical demand distribution where the quantity is uniformly distributed within each range:

| Quantity Sold | Probability | Cumulative Probability |
|---|---|---|
| 100-150 | 0.10 | 0.10 |
| 150-200 | 0.15 | 0.25 |
| 200-250 | 0.25 | 0.50 |
| 250-300 | 0.30 | 0.80 |
| 300-350 | 0.15 | 0.95 |
| 350+ | 0.05 | 1.00 |

The cards cost 99 cents/unit to buy and are sold for $1.79/unit. Cards unsold by St. Valentine's day can neither be sold at a discounted rate nor be stored until the next year. How many cards should this store order for next year?

*(Lecture 4, Slides 23-26)*

3. **Bread** — A supermarket must decide how many loaves of a particular type of whole wheat bread to purchase every day. The daily demand for this type of bread is approximately normally distributed with a mean of 300 and a standard deviation of 50 loaves. A loaf of bread sells for $2.19 and costs the supermarket $1.59. A loaf of bread that is not sold by the end of the day can be sold as a "day old" item the next day for $0.99. How many loaves of this type of whole wheat bread should the supermarket purchase every day?

*(Lecture 4, Slides 27-31)*

4. **Bread Take 2** — A supermarket must decide how many loaves of a particular type of whole wheat bread to purchase every day. The daily demand for this type of bread is approximately normally distributed with a mean of 300 and a standard deviation of 50 loaves. A loaf of bread sells for $2.89 and costs the supermarket $1.59. A loaf of bread that is not sold by the end of the day can be sold as a "day old" item the next day for $0.99. How many loaves of this type of whole wheat bread should the supermarket purchase every day?

*(Lecture 4, Slides 32-35)*

5. **Florida Gator Shirts** — Kohl's sells Florida Gators Gear. Gainesville store manager must decide how many polo shirts to purchase for the 2021 Football Season. Historically, the demand for polo shirts is approximately normally distributed with a mean of 3,000 and a standard deviation of 400 units. A shirt sells for $29.99 and costs the store $12.59. The store estimates the loss-of-goodwill cost to be $10/unit. A shirt that is not sold by the end of the season can easily be sold as a "past season" shirt at the end of the season for $9.99. How many of these polo shirts should the store manager order prior to the 2021 football season?

*(Lecture 4, Slides 45-48)*

6. **Just Around the Corner Bookstore (Full Backlogging)** — Just Around the Corner is a small bookstore in Utopia. Books are replenished weekly from a publishing distributor. Copies of the books that are not sold at the end of a week are still kept on the shelves for future sales. Since Just Around the Corner is the only bookstore in Utopia, if a book is out of stock, then the customers request copies and are willing to wait until the following week. Walter Isaacson's biography of Steve Jobs sells for $35.00 and costs the bookstore $11.95 per book. The owner estimates a loss-of-goodwill cost of $4 each time a book is back-ordered. Weekly demand for Steve Jobs's biography can be approximated by a normal distribution with a mean of 20 and a standard deviation of 8 books per week. The owner uses a weekly interest rate of 5 percent to determine the inventory holding cost. How many copies of the book should be purchased at the beginning of each week?

*(Lecture 4, Slides 65-67)*

7. **Just Around the Corner Bookstore (Lost Sales)** — Recall the previous example. Suppose that a book retailer, Barns, decided to enter the Utopian market and opened a store one block away. Now if Just Around the Corner is out of stock, the customers go and buy a copy from Barns. Using the same parameters (p = $35.00/unit, c = $11.95/unit, b = $4/unit, h = 0.05 × 11.95 = $0.5975/unit, demand ~ Normal(mean=20, std=8)), how many copies of Steve Jobs' biography should the owner of Just Around the Corner order each week?

*(Lecture 4, Slides 80-81)*

8. **Backlogging vs. Lost Sales Conceptual** — Full backlogging optimal order quantity is 29.0112 books. Lost sales optimal order quantity is 36.1744 books. Does this make sense? That is, does it make sense that the optimal order quantity is larger when excess demand is lost as opposed to it being backlogged?

*(Lecture 4, Slide 82)*


## Lecture 5: Inventory - (q,r) Policy

9. **DDLT: Constant Lead Time** — Consider a product for which the weekly demand is normally distributed with a mean of 500 units and a standard deviation of 50 units. If the lead time for the product is 6 weeks, what is the mean and standard deviation of DDLT?

*(Lecture 5, Slide 11)*

10. **DDLT: Random Lead Time** — Consider a product for which the weekly demand is normally distributed with a mean of 500 units and a standard deviation of 50 units. If the lead time for the product is a random variable with a mean of 6 weeks and a standard deviation of 2 weeks, what is the mean and standard deviation of DDLT?

*(Lecture 5, Slide 12)*

11. **Lowe's Paint (Full Backlogging)** — Lowe's uses a continuous review system to track the sales and inventory levels of paint. The weekly demand for a particular type of paint sold is approximately normally distributed with a mean of 40 cans and a standard deviation of 3 cans. The paint has a constant delivery lead time of 12 weeks, and the unit purchase cost is $7.20/can. Fixed cost of ordering is $750/order. Unsatisfied demand can be backlogged into the next cycle. Lowe's estimates the unit loss-of-goodwill cost associated with backlogging is $3/unit. The annual inventory carrying rate is 20 percent and Lowe's operates 52 weeks/year. Determine the optimal order quantity and reorder level for Lowe's.

*(Lecture 5, Slides 38-44)*

12. **Lowe's Paint (Lost Sales)** — Same setup as the previous Lowe's problem (weekly demand ~ Normal(40, 3), lead time = 12 weeks, c = $7.20/can, K = $750/order, b = $3/unit, carrying rate = 20%, 52 weeks/year), but now unsatisfied demand is lost rather than backlogged. Determine the optimal order quantity and reorder level for Lowe's.

*(Lecture 5, Slides 61-64)*

13. **Lowe's Paint (Service Levels)** — Same Lowe's setup (weekly demand ~ Normal(40, 3), lead time = 12 weeks, c = $7.20/can, K = $750/order, carrying rate = 20%, 52 weeks/year), but the manager believes that the loss of goodwill cost cannot be estimated accurately and wants to use a service level of 99%. Determine the policy parameters for Lowe's under (1) Type I service level and (2) Type II service level (you may use the approximate approach).

*(Lecture 5, Slides 71-74)*

14. **Type I Service Level Evaluation** — Consider an item for which the demand per week is approximately normally distributed with a mean of 80 units and a standard deviation of 40 units. This item is replenished from a foreign supplier and the constant lead time is 12 weeks. Currently, the store manager orders 2,000 units when the on-hand inventory level drops down to 1,200 units. What is the Type I Service Level achieved by the current order policy?

*(Lecture 5, Slides 77-80)*

15. **Type II Service Level Evaluation** — Consider an item for which the demand per week is approximately normally distributed with a mean of 80 units and a standard deviation of 40 units. This item is replenished from a foreign supplier and the constant lead time is 6 weeks. Currently, the store manager orders 2,000 units when the on-hand inventory level drops down to 1,200 units. What is the Type II Service Level achieved by the current order policy?

*(Lecture 5, Slides 81-84)*


## Lecture 6: Transportation

16. **Transportation Network Design** — When designing a transportation network: (1) Should transportation be direct or through an intermediate site? (2) Should the intermediate site stock product or only serve as a cross-docking location? (3) Should each delivery route supply a single destination or multiple destinations (milk run)?

*(Lecture 6, Slide 21)*

17. **Cotton / Planet Money T-shirt Activity** — Watch Planet Money "makes a t-shirt" Parts 1, 2, 3. Take notes to develop a flowchart of the flow of goods around the globe.

*(Lecture 6, Slide 31)*

18. **IKEA Logistics Activity** — Watch "The IKEA Group: The story of how we work." Take notes related to their logistics operations, i.e., how they distribute their goods.

*(Lecture 6, Slide 32)*


## Lecture 7: Logistics-A

19. **Togo Shoe Co.** — Togo Shoe Co. produces a line of men's shoes. The company owns a warehouse in San Francisco that supplies retailers on the West Coast. The warehouse operates 360 days/year. Togo has a policy of keeping 1,000 pairs of shoes as safety stock in the warehouse for every day of transportation. A pair of shoes has an average value of $30 and inventory carrying costs are calculated using an interest rate of 30% per year in California and 12% per year while in transit. 70,000 pairs of shoes are sold per year out of the warehouse.

| Mode | Transportation Rate ($/unit) | Door-to-Door Transit Time (days) | Number of Shipments per Year |
|---|---|---|---|
| Rail | 0.10 | 21 | 10 |
| Intermodal | 0.15 | 14 | 20 |
| Truck | 0.75 | 5 | 20 |
| Air | 1.60 | 2 | 40 |

Which mode of transportation minimizes the total logistics costs?

*(Lecture 7, Slides 9-13)*

20. **Caterpillar** — Caterpillar uses a 3PL provider for the shipment of engines to its warehouse in Illinois. Currently, shipments of 20,000 lbs or more are moved at a rate of $5/cwt. If the shipment size falls below 20,000 lbs, a rate of $9/cwt applies. The distribution planning manager has received a rate reduction offer: if Caterpillar agrees to move 40,000 lbs or more in each shipment, the rate will be $3/cwt.

| Information item | Parameter value |
|---|---|
| Annual demand | 5,000 engines/year |
| Warehouse replenishment orders | 43 orders/year |
| Weight of each engine with crate | 175 lbs/engine |
| Standard cost of engine in warehouse | $200/engine |
| Stock replenishment order costs | $15/order |
| Inventory carrying rate | 25%/year |
| Out-of-pocket inventory holding cost | $0.30/cwt |
| Warehouse space | Unlimited |

(cwt = per cent weight, i.e., the unit cost incurred/charged for every 100 lbs shipped.)

Should Caterpillar adjust the replenishment quantity so that the new rate can be used?

*(Lecture 7, Slides 16-20)*

21. **Kroger and Walmart Digital Pricing** — What could happen if the digital price tags were to change depending on the customer?

*(Lecture 7, Slides 22-24)*

22. **Mavi Jeans** — Mavi Jeans is a producer of jeans for men and women. Mavi has a distribution center in New York that receives shipments from production facilities in Bursa, Turkey. From there, jeans are routed to department stores and Mavi stores in North America. Demand in the North American market is approximately 96,000 pairs per year. The facility operates 48 weeks per year. The cost of placing an order with the manufacturing facility in Turkey is about $150 per order. The cost of a pair of jeans is $20 per unit. Inventory holding cost rate is 35% per year at the distribution center. Ms. Blue plans to use the EOQ and a reorder-point policy. Stock-out costs are unknown but the company targets a Type I service level of 90%. Demand during lead time is approximately normally distributed.

| | Horoz Logistics | Speedy Carriers |
|---|---|---|
| Average delivery time (weeks) | 6 | 6 |
| Standard deviation of delivery time (weeks) | 1 | 4 |
| Rate ($/cwt) | 25.00 | 12.50 |

Horoz Logistics offers unlimited liability (in-transit carrying rate 8%/year). Speedy Carriers offers limited liability (in-transit carrying rate 12%/year).

Which carrier should Mavi choose?

*(Lecture 7, Slides 27-36)*


## Problem Set 2: Newsvendor

23. **Taylor Swift Venue** — The manager for Taylor Swift needs to choose a venue for her upcoming North America tour. Past ticket sales show demand can be modeled as a continuous uniform distribution between 50,000 and 70,000 attendees. The average selling price of a seat is $240 whereas the cost of a seat is $50 per seat. How many seats should a venue for the next concert have?

*(Problem Set 2, Problem 1)*

24. **Interior Design Magazine** — The number of the magazine Interior Design sold at the University of Florida bookstore follows a Poisson distribution with an expected number of 4.4 units per month. The purchase cost for the magazine is $15.00 and the sale price is $30.00. By the end of the month, the bookstore can sell all leftover magazines to a second-hand bookstore at a discounted price of $8.00 per unit. What is the optimal number of magazines that the bookstore should order per month?

*(Problem Set 2, Problem 2)*

25. **Northwest Seafood Mussels** — Northwest Seafood in Gainesville buys fresh mussels daily for $4.20 per two-pound bag and sells them for $5.70 per bag. At the end of each business day, any mussels remaining are sold to a cat food producer for $2.40 per bag. If the daily demand for mussels can be approximated by a normal distribution with a mean of 40 bags and a standard deviation of 5 bags, what is the optimal order quantity (in two-pound bags) for mussels?

*(Problem Set 2, Problem 3)*

26. **Bonnie's Strawberries** — Bonnie's is a small grocery store that sells fresh produce. During the strawberry season, demand for fresh strawberries can be approximated using a normal distribution with a mean of 40 quarts per day and a standard deviation of 6 quarts per day. Bonnie estimates the unit cost of overage to be 35 cents per quart.
- (a) If Bonnie orders 49 quarts per day, what is the implied unit cost of underage per quart?
- (b) If the daily demand for mussels can be approximated by a normal distribution with a mean of 40 bags and a standard deviation of 5 bags, what is the optimal order quantity (in two-pound bags) for mussels?

*(Problem Set 2, Problem 4)*

27. **Clyde's Pressure Washers** — The demand for pressure washers at Clyde's U-Rent-It is:

| Demand | Frequency |
|---|---|
| 0 | 0.30 |
| 1 | 0.20 |
| 2 | 0.20 |
| 3 | 0.15 |
| 4 | 0.10 |
| 5 | 0.05 |

The washers are rented by the day only. The profit on the pressure washers is $10 per day. Currently, Clyde has 4 pressure washers.
- (a) Assuming that Clyde's ordering decision is optimal, what is the implied range of unit overage cost per washer?
- (b) Your answer from part (a) has been presented to Clyde, who protests that the amount is too low. Does this suggest an increase or a decrease in the number of pressure washers he stocks? Explain.
- (c) Suppose now that the $10 mentioned as profit is instead the unit overage cost per day per washer and the unit underage cost is unknown. Assuming the optimal number of washers is four, what is the implied range for the unit underage cost per washer?

*(Problem Set 2, Problem 5)*

28. **Rockwell Collins Control Boards** — Rockwell Collins (RC) manufactures control boards for plane cockpit systems. RC has decided to discontinue a particular control board. RC must decide how much to make with the last manufacturing run. RC currently has zero units in stock. Based on past sales data, demand over the lifetime of the product for the existing fleet of planes can be assumed to be Poisson distributed with a mean of 3 units. The unit underage and overage costs are estimated to be $1,000 and $100 per unit, respectively. What is the optimal lifetime buy quantity for this control board?

*(Problem Set 2, Problem 6)*

29. **Swimsuits (Triangular Distribution)** — A retailing firm is to purchase swimsuits for the summer season. The firm buys from a low-cost provider in Asia and can only make a single purchase per year. Selling price p = $20.00/unit, cost = $5.50/unit, salvage value = $2.75/unit, no significant goodwill lost with a lost sale. The purchasing manager believes demand follows a triangular distribution with: D_min = 3,000 units, D_mode = 5,000 units, D_max = 9,000 units.
- (a) What is the unit cost of overage?
- (b) What is the unit cost of underage?
- (c) What is the critical ratio?
- (d) Provide a sketch of the estimated demand distribution.
- (e) What is the optimal order quantity for the swimsuits?

*(Problem Set 2, Problem 7)*

30. **Happy Henry's EX123 Cars** — Happy Henry's car dealer sells an imported car called the EX123. Every three months, a shipment is made to Happy Henry's. Emergency shipments can be made between intervals (two weeks, and buyers are willing to wait that long, but will go elsewhere before the next three-month shipment). Demand over a three-month interval is normally distributed with a mean of 60 and a variance of 36. The cost of holding an EX123 for one year is $500. Emergency shipments cost $250 per car over and above normal shipping costs.
- (a) How many cars should Happy Henry's be purchasing every three months?
- (b) Repeat the calculations, assuming that excess demands are backordered from one three-month period to the next. Assume a loss-of-goodwill cost of $100 for customers having to wait until the next three-month period and a cost of $50 per customer for bookkeeping expenses.
- (c) Repeat the calculations, assuming that when Happy Henry's is out of stock, the customer will purchase the car elsewhere. The cars cost Henry an average of $10,000 and sell for an average of $13,500. Ignore loss-of-goodwill costs for this calculation.

*(Problem Set 2, Problem 8)*
