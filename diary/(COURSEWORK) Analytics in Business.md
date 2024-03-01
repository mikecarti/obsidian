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
Consumer segment seems the most profitable from all options. **But for some regions such as Canada, LATAM, APAC  and EMEA Corporate sector contains a very small portion, so it maybe profitable to concentrate on other sectors in these regions**. 
## Profit by Region and category
Central EU sector is buying the most of Office Supplies. While North APAC is purchasing most of technology, and Furniture. It is vital to ensure that these sectors get the best possible service and quality, as they are very profitable.  




# Geographic Analysis 
![[Geography Economics 1.png]]
We can compare average profits and average shipping cost. Comparing it gives us a hint, that **regions with *high* shipping cost will likely be highly profitable**. Such examples include Mali, Democratic Republic of Congo, Uruguay to name a few. **Regions like Kazakhstan, Argentina, Sweden, Zimbabwe, Turkmenistan have very low profitability, and should be examined deeper**.


## Non-Profitable regions
![[Non-Profitable Regions.png]]

Considering the non-profitable regions, let us analyze lossful regions. The most lossful regions from this analysis are represented in the table below (C - consumer, B - Business, G - Home Office). **In order to cut losses, it may be beneficial to change the selling strategy in those regions, or to stop selling some categories to lossful segments.** Here is the table of most lossful markets, that could be reworked: 

|     | Furniture                                   | Office Supplies      | Technology            |
| --- | ------------------------------------------- | -------------------- | --------------------- |
| C   | Africa, EMEA, Central, South, Southern Asia | Africa, Central,EMEA | Africa, Central, EMEA |
| B   | Africa, EMEA, Central                       | Africa, EMEA         | Africa,  EMEA         |
| G   | Africa, EMEA, Central, North                | EMEA                 | EMEA                  |

By reducing losses from lossful markets, company may become more profitable. 


## Non-profitability of Table product. 
![[Tables Profitability.png]]

As it was apparent from the first slide with graphs, tables are the most lossful sub-category. As it turned out average shipping cost is extremely high (highest from all of the sub-categories), that in theory could be the problem with net losses that are occuring because of selling tables. While examining geographical view, we can see, that the biggest buyers are USA, China, Australia, Brazil, Mexico and India (as well as several european countries). 

![[Pasted image 20240301220652.png]]

So it is apparent, that those big markets, that are those high buyers of tables, are really profitable. But if we are trying to examine other markets, there are some lossful ones

![[Pasted image 20240301221126.png]]

What is interesting about those markets. They do not buy a lot of tables, they are pretty small sellers, but they make company's profits smaller. **Thus it is advised to change company's strategy until it becomes profitable to sell tables in these regions or stop selling tables there.** What is actually a very valuable insight is that this analysis into countries in which tables sell poorly also opened our eyes on other non-profitable products. It seems like on average in those countries all products are anti-profitable. The most non-profitable would be Phones, Bookcases, appliacnces, chairs and copiers. It's also noticeable that they have very high shipping cost. **Maybe some logistic strategies that could lower shipping costs could make these products profitable for those regions.** **Otherwise products, that drive company's profits in negative direction from these regions should be canceled out of purchasing for non-profitable countries such as Turkey, Nigeria, etc**.


## Summary: 
 - **It is advisable to choose business strategies that allow low shipping costs only for profitable regions, categories and markets.**
 - **But for some regions such as Canada, LATAM, APAC  and EMEA Corporate sector contains a very small portion, so it maybe profitable to concentrate on other sectors in these regions**
 -  **regions with *high* shipping cost will likely be highly profitable**
 - **Regions like Kazakhstan, Argentina, Sweden, Zimbabwe, Turkmenistan have very low profitability, and should be examined deeper**.
 - **In order to cut losses, it may be beneficial to change the selling strategy in those regions, or to stop selling some categories to lossful segments.**
 - **it is advised to change company's strategy until it becomes profitable to sell tables in these regions or stop selling tables there.**
 - **Maybe some logistic strategies that could lower shipping costs could make these products profitable for those regions.** **Otherwise products, that drive company's profits in negative direction from these regions should be canceled out of purchasing  for non-profitable countries such as Turkey, Nigeria, etc
 