# Power BI Sales Analytics

## 🧩Problem Statement
Businesses deal with sales data coming from many angles different products, customers, cities, promotions, and time periods. While this data contains valuable information, it is often stored in detailed tables that make it hard to quickly understand how the business is really performing. Questions like Which products are selling the most? Which ones are hurting profits? Are promotions actually working? are not easy to answer by just looking at raw data.

This project focuses on turning that sales data into a clear and interactive Power BI dashboard using a star schema model. By visualizing sales, profit, and quantity across cities, products, promotions, and time, the dashboard helps users quickly spot trends, identify top and bottom performers, and understand the overall health of the business. The goal is to make sales insights easy to explore and useful for everyday business decisions.

&nbsp;

## 📋Objectives
* Identify the top and bottom five products based on sales, profit, and quantity sold to clearly understand product-level performance.

* Understand how sales change over time by analyzing daily, monthly, quarterly, and yearly trends.

* Explore the relationship between sales and profit to see how revenue translates into profitability.

* Enable comparison between any two selected time periods, allowing users to evaluate performance changes in sales, profit, and quantity sold.

* Analyze average discounts across different discount categories to understand promotional strategies and pricing behavior.

* Track the total number of orders to measure overall business activity and demand levels.

* Provide detailed order-level visibility, showing sales, profit, discount, net sales, and related fields with flexible filtering options.

* Allow users to filter data by product, date, customer ID, and promotion category for deeper and more focused analysis.

* Examine sales performance across different cities to identify geographic patterns and regional strengths.

&nbsp;

🛠 Tools & Technologies

* Power BI Desktop – Data cleaning, transformation, DAX measures, and dashboard creation

* Microsoft Excel .xlsx – Source data for fact and dimension tables

* Power Query Editor – Conditional columns, merges, and data type correction

* Star Schema Data Model – One-to-many relationships with single-direction filtering

* Final Dataset – Cleaned and structured data ready for analysis

Techniques Applied:

* Data Cleaning and Transformation

* Fact Dimension merging and calculations

* Interactive visuals (KPIs, Matrix, slicers, bookmarks)

&nbsp;


🔄 Project Workflow

1️⃣ Data Import and Initial Setup

The dataset was imported into Power BI, and all four required tables were selected from the import dialog box. The data was then opened in Transform Data mode to begin cleaning and preparation.

2️⃣ Power Query Transformation

In Power Query Editor:

* Tables were renamed appropriately to represent fact and dimension tables.

* Data types were corrected for all columns in the four dimension tables to ensure consistency and accuracy.

3️⃣ Handling Promotion Data Issues

In the Dim Promotion table, the Price Reduction Type column could not be converted to a numeric data type due to text values.
To resolve this:

* A conditional column named Percentage was created.

* Discount values were assigned based on promotion codes.

* The new column was successfully converted to a whole number, creating the required discount percentage field.

4️⃣ Resolving Missing Values in the Fact Table

Several key columns in the Fact Table contained empty values, including:

* Price per Unit

* Total Sales

* Discount Percentage

* Discount Value

* Net Sales

Each issue was resolved as follows:

Price per Unit

* A merge query was performed between the Fact Table and Dim Product using Product ID.

* A left join was applied, and the Price per Unit column was extracted into the Fact Table.

Total Sales

* A custom column was created by multiplying Units Sold × Price per Unit.

Discount Percentage

* The Fact Table was merged with Dim Promotion using Promotion ID.

* A left join was applied, and the Discount Percentage column was extracted.

Discount Value

* A custom column was created using the formula:
(Total Sales × Discount Percentage) / 100

Net Sales

* A custom column was created by subtracting Discount Value from Total Sales.

5️⃣ Final Data Preparation

After completing all calculations:

* Data types for all columns were verified and corrected.

* Changes were applied using Close & Apply.

* The dataset was now clean and ready for reporting.

6️⃣ Data Modeling (Star Schema)

In the Model View:

* One-to-many relationships were created from each dimension table to the fact table.

* Relationships were arranged in a star schema format.

* Single-direction filtering was enabled for all dimension tables to ensure efficient and accurate filtering.

7️⃣ Visualization and Slicer Setup

Relevant visuals and slicers were created to meet all project requirements, including KPIs, trend analysis, top/bottom analysis, and matrix visuals.

8️⃣ Dynamic Slicer Interaction (Advanced Requirement)

To ensure slicers on the Matrix Visual page interacted dynamically:

*  DAX measure was created:
Sum Dim = SUM('Fact Table'[Net Sales])

* This measure was added to each slicer’s Filters pane.

* The filter condition “Show items when value is not blank” was applied.

* This ensured slicers dynamically adjusted based on selections, improving user interaction and usability.

9️⃣ Final Outcome

The final model and visuals provide a fully interactive sales analytics dashboard, fulfilling all functional requirements and enabling effective, data-driven analysis.

&nbsp;

## 💡 Key Insights
* Sales and profit generally move hand in hand, showing that products with higher sales tend to generate higher profits, with only a few exceptions at the individual product level.

* A small number of products account for a large share of overall sales and profit, while many others contribute very little, suggesting the need to focus more on high performers and rethink weaker items.

* Promotions help boost sales volumes but don’t always increase profitability, indicating that heavy discounting can reduce margins even when sales rise.

* Some cities consistently deliver stronger sales than others, highlighting regions with higher demand and potential opportunities for targeted expansion.

* Several low-performing products continue to show weak sales and profit over time, making them suitable candidates for repositioning, improvement, or possible discontinuation.

🔗 Screenshots
## <img width="1920" height="1080" alt="Screenshot 2026-01-01 162226" src="https://github.com/user-attachments/assets/f725ee0b-87ad-4762-bf57-a1c83e7377f6" />

&nbsp;

<img width="1920" height="1080" alt="Screenshot 2026-01-01 162334" src="https://github.com/user-attachments/assets/3b7280c8-7a29-44e0-8647-bc1f2f231af7" />

&nbsp;

<img width="1920" height="1080" alt="Screenshot 2026-01-01 162424" src="https://github.com/user-attachments/assets/ebe75e0b-4903-42eb-80dc-85595446d947" />

&nbsp;
<img width="1920" height="1080" alt="Screenshot 2026-01-01 162604" src="https://github.com/user-attachments/assets/93610d4c-2de1-4de1-aae3-1c9825ab5e83" />





