# Exam 2 Practice Questions (Generated)

## Newsvendor

### Question 1 (Lecture 4, p. 19)
Recall the single period profit maximization newsvendor model. Fill in the blanks.

a. Everything else being equal, if the selling price per unit goes up, the optimal order quantity _____________

b. Everything else being equal, if the unit salvage revenue goes up, the optimal order quantity _____________

c. Everything else being equal, if the unit purchase cost goes up, the optimal order quantity _____________

d. Everything else being equal, if the unit loss of goodwill cost goes down, the optimal order quantity _____________


### Question 2 (Lecture 4, pp. 27-28)
A local bakery prepares specialty cupcakes for a weekly weekend event. Based on the past year of data, the demand for specialty cupcakes is normally distributed with a mean of 4,800 cupcakes and a standard deviation of 1,200 cupcakes. The cost of producing a specialty cupcake is $3.00 per cupcake, and they are sold for $8.50 per cupcake. The manager estimates that the unit loss of goodwill cost for the specialty cupcakes is $2.00 per cupcake. Any unsold specialty cupcakes must be discarded at the end of the event.

a. How many specialty cupcakes should the bakery prepare for the next weekend event?

b. What should the unit loss of goodwill cost be, for the optimal number of cupcakes to be 6,000?


### Question 3 (Lecture 4, pp. 65-67, 80-81)
A distributor sells specialty printer ink cartridges to businesses in its area on a weekly basis. Any cartridges unsold at the end of the week can be stocked and sold during the next week. The weekly demand for the cartridges is approximately normally distributed with a mean of 180 units and a standard deviation of 30 units. It costs the distributor $40 to procure each cartridge, and sells each cartridge for $55 to its customers. The distributor estimates that the unit loss of goodwill per cartridge is $20. The distributor incurs an inventory holding cost of $2 per cartridge per week.

a. Suppose that the business customers who buy from the distributor are patient, and, hence, are willing to wait for a week if the distributor cannot immediately provide the cartridges they need. What is the optimal order quantity for the distributor?

b. Suppose that the business customers who buy from the distributor are impatient, and, hence, find an alternative supplier immediately to obtain the cartridges they need. What is the optimal order quantity for the distributor?


## (q,r) Policy

### Question 1 (Lecture 5, p. 38)
(q,r) policy under full backlogging: GreenLeaf Garden Supplies sells organic fertilizer through their online store. The monthly demand for a particular slow-release fertilizer is approximately normally distributed with a mean of 400 bags and a standard deviation of 48 bags. GreenLeaf operates 12 months throughout the year. The replenishment lead time for this fertilizer is 3 months. For each replenishment, GreenLeaf incurs a fixed ordering cost of $600 per order and an annual inventory holding cost of $3/bag/year. The unit loss-of-goodwill cost associated with this type of fertilizer is $4/bag.

a. What are the parameters of demand during lead time?

b. What are the order quantity and the reorder level at the end of iteration 1? NOTE: You may stop after completing j=1. Once you determine the z_j, round it down to two digits after the decimal point, and use that value to interpolate.

c. What is the expected safety stock level if you operated the system using the policy parameters you determined in part (b)?

d. What is the average annual total cost if the system were operated using the policy parameters you determined in part (b)? NOTE: Please ignore the total annual purchasing component for this calculation, since unit cost per unit, c, is not given in the problem statement.


### Question 2 (Lecture 5, pp. 72-73)
System Design using Service Levels: AutoParts Direct sells a specialized brake sensor. The weekly demand for the sensor is approximately normally distributed with a mean of 250 units and a standard deviation of 45 units. AutoParts Direct operates 52 weeks throughout the year. The replenishment lead time from their supplier is 4 weeks. For each replenishment, AutoParts Direct incurs a fixed ordering cost of $700 per order and an annual inventory holding cost of $2.00/sensor/year.

a. What are the parameters of demand during lead time?

b. The owner of AutoParts Direct is interested in using a (q,r) policy to replenish the inventory for the sensor. If the owner wants to ensure a Type I service level of 98%, what should the order quantity and reorder level be?

c. The owner of AutoParts Direct is interested in using a (q,r) policy to replenish the inventory for the sensor. If the owner wants to ensure a Type II service level of 98%, what should the reorder level be? You may use the order quantity you determined in part (b).


### Question 3 (Lecture 5, pp. 77, 81)
System Assessment using Service Levels: FreshVita Supplements manufactures a popular vitamin blend. Due to the specialized production process, the lead time to replenish stock takes about 4 weeks. The weekly demand for the supplement is approximately normally distributed with a mean of 150 bottles and a standard deviation of 18 bottles. Currently, the owner of the company sets up a production run to produce 1,200 bottles, when the on-hand inventory level for the supplement drops down to 640 bottles.

a. What is the expected Type I service level performance of the current policy? Please report 4 digits after the decimal. Interpolate for the z value with 4 digits after the decimal.

b. What is the expected Type II service level performance of the current policy? Please report 4 digits after the decimal. Interpolate for the z / L(z) value with 4 digits after the decimal.
