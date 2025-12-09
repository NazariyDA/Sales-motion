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


## 🛠 The dashboard includes the following key features:
* **Key Performance Indicators (KPIs) at the top:** Total Units Sold, Total Sales Revenue, Average Revenue per Customer, and Average Revenue per Product.
* **Comparative Visualization:** Revenue comparison with the previous year (YoY) for 2023 and 2024, monthly revenue trends, and revenue by weekdays and weekends.
* **Category Analytics:** Revenue by category and top-performing products driving sales.
* **Customer Analytics:** Top 5 customers generating the highest revenue, revenue contribution by gender, and revenue distribution across age segments.
* **Regional Analytics:** Regional sales performance and revenue distribution by segment.
* **Interactivity:** Ability to filter by product categories (Clothing, Electronics, Food, Home Appliances, Sports) and by region (East, North, South, West).
<img width="1000" height="625" alt="image" src="https://github.com/user-attachments/assets/a58707ac-f491-4794-a258-43cb49dbae5c" />



:pushpin: Interactive Dashboard: [From Data to Insights](./Interactive%20Dashboard.xlsx)

### Thank you for your interest in this project 🏆






