# :bar_chart: Sales motion
Sales motion - is an interactive dashboard in Excel designed for in-depth analysis of sales and key business metrics. It combines data on **sales**, **products**, and **customers**, providing a comprehensive view of the company’s performance. 
It is ideal for **sales managers**, **analysts**, and **business executives** who aim to quickly evaluate performance, identify trends, and make data-driven decisions.

:pushpin: Data source: [Excel Dashboard Dataset](./Excel%20Dashboard_Dataset.xlsx)

## 🧱 Used technologies
🧩 MS Excel 
 <details>
  <summary>Classic Excel formulas (IF, Addition, Subtraction, Division, Multiplication)</summary>

 **Revenue %:**



      =S7/SUM($S$7:$S$8)
      
 **Label:**

  
    =IF(
        L5 >= 1000000000;
        TEXT(L5 / 1000000000; "$0") & "B";
        IF(
            L5 >= 1000000;
            TEXT(L5 / 1000000; "$0") & "M";
            IF(
                L5 >= 1000;
                TEXT(L5 / 1000; "$0") & "K";
                "0"
            )
        )
    )


</details>

🧩 Power Pivot (data cleaning and transformation) 
 <details>
  <summary>DAX (SUMX, DIVIDE, Distinctcount, CONCATENATE, FORMAT and others)</summary>
 
   **Total Revenue:**



      =SUMX(
        'Transaction';
        'Transaction'[Quantity] * 'Transaction'[UnitPrice]
      )
   
   **AVG Revenue per customer:**



     =DIVIDE(
        [Total Revenue];
        [# Customer]
     )

  **Customer:**


      =DISTINCTCOUNT(
        'Transaction'[CustomerID]
      )

 **Quarter:**



      =CONCATENATE(
        "Квартал";
        INT((MONTH([Date]) + 2) / 3)
      
  **Data Format:**



      =FORMAT(
        [Date];
        "MMM"
      )

</details>

## <img width="25" height="25" alt="image" src="https://github.com/user-attachments/assets/2e00bec0-d629-4368-9657-90e933350f74" /> General overview
The database contains **5,000** sales records for the years **2023–2024**, with a total revenue of **$ 14,536,589** and a total of **28,651** items sold. 

The data covers 50 products, 300 customers, regions, gender, and age groups.
## 🛠 The dashboard includes the following key features:
* **Key Performance Indicators (KPIs) at the top:** Total Units Sold, Total Sales Revenue, Average Revenue per Customer, and Average Revenue per Product.
* **Comparative Visualization:** Revenue comparison with the previous year (YoY) for 2023 and 2024, monthly revenue trends, and revenue by weekdays and weekends.
* **Category Analytics:** Revenue by category and top-performing products driving sales.
* **Customer Analytics:** Top 5 customers generating the highest revenue, revenue contribution by gender, and revenue distribution across age segments.
* **Regional Analytics:** Regional sales performance and revenue distribution by segment.
* **Interactivity:** Ability to filter by product categories (Clothing, Electronics, Food, Home Appliances, Sports) and by region (East, North, South, West).
<img width="1000" height="625" alt="image" src="https://github.com/user-attachments/assets/a58707ac-f491-4794-a258-43cb49dbae5c" />

:pushpin: Interactive Dashboard: [From Data to Insights](./Excel%20Dashboard_Dataset%20Edit%20Version.xlsx)

## <img width="25" height="25" alt="image" src="https://github.com/user-attachments/assets/6793dbc4-3d2d-4088-bf15-df94174bfd8f" /> Conclusions and Recommendations Based on the Elvion Dashboard Analysis:
* ### Annual Trends
Revenue increased from 2023 to 2024, accompanied by a corresponding rise in the number of sales. The year 2024 demonstrates better performance, with higher revenue per unit.
| Year | Revenue | Quantity | Revenue Change (YoY) |
|------|----------|-----------|------------------------|
| 2023 | 6,774,586 | 13,494 | – |
| 2024 | 7,762,003 | 15,157 | +15% |


<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/48c4ff08-2a9d-4d3c-9718-eee6f10e87a1" /> **Conclusions:** Steady growth, possibly driven by product range expansion or marketing efforts.

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/f35489d1-c8a5-4471-9b95-d5fb263625ac" /> **Recommendation:** Forecast further growth, but monitor expenses to maintain profitability.

* ### Analysis by Categories
The “Sports” category is the revenue leader, with other categories showing similar but slightly lower performance. All categories are profitable, but focusing on “Sports” could drive faster growth.
| Category        | Revenue    |
|-----------------|------------|
| Sports          | 3,104,273  |
| Home Appliances | 2,919,114  |
| Groceries       | 2,888,747  |
| Electronics     | 2,821,121  |
| Clothing        | 2,803,334  |

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/48c4ff08-2a9d-4d3c-9718-eee6f10e87a1" /> **Conclusions:** Sports (e.g., Skipping Rope, Running Shoes) and Home Appliances (Vacuum Cleaner) generate high revenue. Groceries and Electronics remain stable but may require promotional activities.

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/f35489d1-c8a5-4471-9b95-d5fb263625ac" /> **Recommendation:** Expand the product range in the top-performing categories.

* ### Sales by Region
West and East generate approximately 70% of revenue, while North is the weakest-performing region.
| Region | Revenue    |
|--------|------------|
| West   | 5,230,417  |
| East   | 4,887,084  |
| South  | 3,612,920  |
| North  | 806,168    |

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/48c4ff08-2a9d-4d3c-9718-eee6f10e87a1" /> **Conclusions:** West and East are the key markets. North may be underperforming due to demographics or logistics.

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/f35489d1-c8a5-4471-9b95-d5fb263625ac" /> **Recommendation:** Increase marketing efforts in North and South to achieve better balance.

* ### Analysis by Gender and Age Groups
Women generate nearly twice as much revenue as men. Young and middle-aged adults (19–56 years) are the primary buyers.

| Gender | Revenue    |
|--------|------------|
| Female | 9,384,843  |
| Male   | 5,151,746  |

| Age Group | Revenue    |
|-----------|------------|
| 19–37     | 6,091,978  |
| 38–56     | 5,568,339  |
| 57–75     | 2,815,487  |
| 0–18      | 60,785     |
| 76+       | 0          |

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/48c4ff08-2a9d-4d3c-9718-eee6f10e87a1" /> **Conclusions:** Focus on the female audience and young adults (e.g., sports products for ages 19–37).

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/f35489d1-c8a5-4471-9b95-d5fb263625ac" /> **Recommendation:** Launch targeted campaigns for older age groups and men.

* ### Top Customers by Revenue
The top 5 clients generate a total revenue of 482,268, which accounts for 3.32% of the total revenue (14,536,589)

| Customer         | Revenue   |
|-----------------|-----------|
| James Adams      | 116,129   |
| Kimberly Cook    | 96,583    |
| Benjamin Stewart | 92,809    |
| Kathleen Kelly   | 88,769    |
| Kevin Gutierrez  | 87,978    |

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/48c4ff08-2a9d-4d3c-9718-eee6f10e87a1" /> **Conclusions:** These clients are likely the most loyal or have the largest orders.

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/f35489d1-c8a5-4471-9b95-d5fb263625ac" /> **Recommendation:** Develop loyalty programs (discounts, personalized offers) to retain them, while continuing to diversify the client base to reduce risks (for example, by attracting new clients through marketing in regions with low sales)

* ### Top Products and Underperforming Items
The top 10 products are mostly sports items and home appliances. Underperforming items are basic products with low revenue.

| Top Product       | Revenue   | Underperforming Product | Revenue   |
|------------------|-----------|------------------------|-----------|
| Vacuum Cleaner    | 433,638   | Sugar Pack             | 216,362   |
| Skipping Rope     | 358,365   | Refrigerator           | 228,513   |
| Running Shoes     | 352,661   | Socks                  | 246,808   |
| Flour             | 337,960   | Bread                  | 251,269   |
| Tablet            | 333,200   | Printer                | 251,622   |
| Tennis Racket     | 330,413   | Smartwatch             | 253,026   |
| Microwave         | 322,208   | Fan                    | 256,709   |
| Canned Beans      | 321,552   | LED TV                 | 256,980   |
| Swimming Goggles  | 320,632   | Dress                  | 258,936   |
| Yoga Mat          | 315,784   | Blender                | 259,987   |

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/48c4ff08-2a9d-4d3c-9718-eee6f10e87a1" /> **Conclusions:** Top products are highly profitable; underperforming items may require rebranding or discounts.

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/f35489d1-c8a5-4471-9b95-d5fb263625ac" /> **Recommendation:** Remove the weakest items from sale or improve their marketing.

* ###  Monthly Trends (Seasonality)
Revenue is stable, with peaks in January (likely due to New Year purchases) and November (holiday season)

| Month     | Revenue    |
|-----------|------------|
| January   | 1,439,383  |
| February  | 1,189,456  |
| March     | 1,240,338  |
| April     | 1,170,425  |
| May       | 1,276,021  |
| June      | 1,038,266  |
| July      | 1,088,215  |
| August    | 1,199,136  |
| September | 1,213,886  |
| October   | 1,103,064  |
| November  | 1,351,187  |
| December  | 1,227,212  |

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/48c4ff08-2a9d-4d3c-9718-eee6f10e87a1" /> **Conclusions:** Low-revenue months (June) are ideal for promotions.

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/f35489d1-c8a5-4471-9b95-d5fb263625ac" /> **Recommendation:** Plan inventory for Q1 and Q4.

* ###  Trends by Day of the Week
Weekdays generate approximately 71% of revenue, with Wednesday being the peak.

| Day       | Revenue    |
|-----------|------------|
| Wednesday | 2,234,903  |
| Friday    | 2,202,043  |
| Saturday  | 2,177,201  |
| Monday    | 2,041,124  |
| Sunday    | 2,024,299  |
| Thursday  | 1,957,508  |
| Tuesday   | 1,899,511  |

| Week Type | Revenue    |
|-----------|------------|
| Weekday   | 10,335,089 |
| Weekend   | 4,201,500  |


<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/48c4ff08-2a9d-4d3c-9718-eee6f10e87a1" /> **Conclusions:** Most sales occur on weekdays; weekends are stable.

<img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/f35489d1-c8a5-4471-9b95-d5fb263625ac" /> **Recommendation:** Run promotions on Tuesday/Thursday to balance revenue.




### Thank you for your interest in this project 🏆


















