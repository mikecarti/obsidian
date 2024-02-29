# Dataset Description

To effectively engage with the dataset, an initial step involved comprehensive study. Primarily, I commenced by generating and scrutinizing all available charts. This exploration revealed the dataset's focus on global market transactions encompassing various goods, accompanied by detailed records of sales, deliveries, dates, modes of delivery, quantities, among other pertinent details.
## Interesting Columns
- Ship Mode - (First Class, Same Day, Second Class, Standard Class)
- Segment - (Consumer, Corporate, Home Office). Home office - ministerial department of the Government. So we can also think about those as Consumer Segment, Business Segment and Government Segment.
- City - Supposedly the city where the delivery is coming
- State - The state where delivery is coming
- Country - The country where delivery is coming
- Postal Code - The Postal Code where delivery is coming
- Market - Global region (Africa, APAC, Canada, EMEA, EU, LATAM, US)
- Region - More local region than Market (for example North Asia, Oceania)
- Category - (Furniture, Office Supplies, Technology)
- Sub-Category - includes 17 sub-categories of sold products. Examples: Art, Phones, Storage, Bookcases...
- Sales - Cost of an order
- Quantity - Quantity of a product bought within an order
- Discount - Discounts (0, 0.85)
- Profit - Profit made from an order  (-6 599,978 to 8 399,976)
- Shipping Cost - cost of the delivery (0,002 to 933,57)
- Order Priority - (Low, Medium, High, Critical)

# Getting Familiar With Data
![[Overall Profits.png]]

### Seasonality
We can see that our profits are seasonal - from 1st quarter to 4th profits rise

### Dynamic of products
It is apparent that there are some high profit sub-categories and low profit. in this research i choose tactic to optimize non-profitable and low profitable domains of this business. 

### Profits for products / Clients. 
On a density map it can be seen that some products can have negative product, and the most of products have relatively low profitability.



# Deeper overall analysis.
![[Segment and Categories.png]]

## Profits and Delivery Density.
It is apparent, that low shipping costs frequently negatively influence profits and may even turn them into negative profits. **It is advisable to choose business strategies that allow low shipping costs only for profitable regions, categories and markets.**

## Ship Mode and Category
For average profit the most profitable category is technology, ?it will be apparent later that it is due to low costs of delivering technology products?. Office supplies having the least average shipping cost, have very small average profit compared to other categories. First Class and Same Day ship modes cost the most to ship on average, but same day delivery is really non-popular choice. Removing same day option may actually reduce costs.

## Profit by Region/Segment
Consumer segment seems the most profitable from all options. **But for some regions such as Canada, LATAM, APAC  and EMEA Corporate sector contains a very small portion, so it maybe profitable to concentrate on other sectors in these regions**. f
## Profit by Region and category
Central EU sector is buying the most of Office Supplies. While North APAC is purchasing most of technology, and Furniture. It is vital to ensure that these sectors get the best possible service and quality, as they are very profitable.  




# Geographic Analysis 
![[Geography Economics 1.png]]
We can compare average profits and average shipping cost. Comparing it gives us a hint, that **regions with *high* shipping cost will likely be highly profitable**. Such examples include Mali, Democratic Republic of Congo, Uruguay to name a few. **Regions like Kazakhstan, Argentina, Sweden, Zimbabwe, Turkmenistan have very low profitability, and should be examined deeper**.


## Non-Profitable regions
![[Non-Profitable Regions.png]]

Considering the non-profitable regions, (think about something given that dataL: africa is lossful on consumer furniture, EMEA is lossful on corporate TECH, )