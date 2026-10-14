
# 3.1 Excel 

In Excel, there are **two primary ways** to create charts to visualize your data:

1. Creating a chart from a simple worksheet
    
2. Creating a pivot chart from a pivot table

### **Creating a Chart from a Simple Worksheet**

**Process:** Simply highlight the data, go to the **Insert** tab, and choose the type of chart that best fits your data. Excel will generate the chart based on the selected data range. The first example is on Windows and the second on Mac.

>**When to Use**: This method is ideal for straightforward datasets where you don't need complex data summarization. It's perfect for visualizing raw data that is already organized in a table.


### **Creating a Pivot Chart from a Pivot Table**

**Process:** First, create a PivotTable to organize and summarize your data. Then, insert a PivotChart based on the PivotTable, and Excel will generate a chart reflecting the summary of the data.

>**When to Use**: Pivot Charts are useful for analyzing larger or more complex datasets where you need to summarize and dynamically interact with the data. They are ideal when you want flexibility in how the data is presented and analyzed.

## Power BI

**The Report View** in Power BI is where you create, design, and interact with your charts and visualizations.

**The Canvas** is the primary area where you create and arrange your visualizations. When you first load data in Power BI Desktop, you see the Report view with a blank canvas.

**The Data Pane** (previously known as Fields pane) is located on the right side of the screen and displays all the available data fields from your dataset. It allows you to select and drag fields to the Canvas to create various types of visualizations.

	**Data Organization**: Displays tables and fields (columns) from the dataset, helping you easily find the data you need for visualizing.

	**Drag and Drop**: Simply drag fields from the Data Pane to the Canvas to generate different types of charts.

	**Measures & Calculations**: You can create custom calculations or measures in this pane for more complex visualizations.

**The Visualizations Pane** shows all the available chart types that you can use to visualize your data.

At the bottom of the charts, you can assign fields to various parts of your visualizations, such as axis, values, legends, and tooltips. As an example, we choose the bar chart, drag the product ID into the y-axis section, and the Sales field into the x-axis section.

## Advanced Editor & Add Column in Query Editor

The language used in Power BI and shown in the Advanced Editor is the Power Query "M" Language.

- "M" is a case-sensitive language.  
    
- "M" statements contain programming elements such as functions, variables, expressions,  primitive, and structured values that create a formula with the logic required to transform the data.
    
- "M" queries have a single "let" expression that contains the code for the procedural steps to shape and transform the data.
    
- Statements are constructed by a "let" statement, followed by an "in" statement. The "in" statement returns the value of the variable that becomes the final shaped data in Power BI.
- 
The **key difference** is that **calculated columns work with data after it has been brought into Power BI,** whereas **adding columns through the Query Editor works with the raw data coming in.** The new data in the added columns is available for report authors and users to explore and use in formulas, as they would any other data.

![[Pasted image 20261012163724.png]]


# 3.2 Calculated Column with DAX

A **calculated column** is a column in your dataset where the values are generated based on a formula, rather than being directly imported from a data source.

![[Pasted image 20261012163904.png]]

### Syntax

![[Pasted image 20261012163921.png]]

## Common DAX Functions

#### Aggregation

![[Pasted image 20261012164039.png]]

#### Counting

![[Pasted image 20261012164054.png]]

#### Logical

![[Pasted image 20261012164125.png]]
#### Text 

![[Pasted image 20261012164138.png]]
#### Date and time

![[Pasted image 20261012164146.png]]

##  Creating Calculations with DAX

1. Create a calculated column to combine product ID and product name.
2. Use the Product calculated column in a visualization.
3. Create a calculated column for cost
4. Create an area chart that uses the Cost calculated column.

## Conditional Columns

Conditional columns are incredibly helpful for **grouping** and **organizing data**. Instead of manually going through hundreds or thousands of rows and labelling them, we can set up a simple rule, and the computer will do it for us!

![[Pasted image 20261012164509.png]]

>First, **IF** the 'Quantity' in the 'Orders' column is greater than 99, **THEN** set the 'Priority' to 'High'. That's exactly what it's saying in the first callout box. Then, we move to the second part: **IF** the 'Quantity' is less than 5, **THEN** set the 'Priority' to 'Low'. And finally, if neither of those conditions are met, we set the 'Priority' to 'Medium'. This covers all the remaining scenarios.

## Calculated & Quick Measures

**Calculated Measures** show our data at **a different level of detail** for analysis. Think of it like zooming in or zooming out on your data. Instead of just seeing the raw numbers, we can use measures to calculate things like averages, totals, or percentages, giving us a more meaningful picture.

![[Pasted image 20261012164702.png]]

## Measure Aggregation Types

**There are three main types of measure aggregations: Additive, Non-additive, and Semi-additive. Each type has its own rules and considerations.**
### **Additive**

**Additive** measures can be summed across **_all_ dimensions** of a dataset. Think of it like adding up all the pieces of a puzzle – the total still makes sense. Examples include 'Sales Amount', 'Quantity Sold', and 'Cost'.

If you have sales data for different regions and time periods, you can simply add up the sales from each region and each time period to get the total sales.![[Pasted image 20261012164907.png]]

### Non-additive

**Non-additive** measures cannot be meaningfully summed across all dimensions. If you try to add them up, you'll get incorrect or nonsensical results. Examples include 'Ratios', 'Averages', and 'Percentages'.

Imagine you're looking at the average test scores for different classes. Adding up the averages of each class wouldn't give you the overall average test score for all classes. It just doesn't work that way. Similarly, adding percentages or ratios across different groups often leads to misleading conclusions.

### Semi-additive

**Semi-additive** measures are a bit trickier. They can be summed across _some_ dimensions, but not others. They have restrictions on which dimensions you can aggregate over. Examples include 'Inventory Levels', 'Account Balances', and 'Headcount'.

Let's say you have daily inventory levels for a warehouse. You can't simply add up the daily inventory levels to get the total inventory for the month. However, you might be able to find the average inventory level for the month or the inventory level at the end of the month. It depends on the specific question you're trying to answer.
![[Pasted image 20261012165007.png]]


## Filter Manipulation

**Row context** exists when DAX evaluates an expression for each row of a table. It's the "current row" perspective. When you create a calculated column, DAX goes row by row, and the formula uses the values from that specific row

##### Example

If you have a "Sales" table with "Quantity" and "Price" columns, a calculated column "Total Sales" using [Quantity] * [Price] will multiply the values of those columns for each individual row.
![[Pasted image 20261012165130.png]]

### Filter Context

**Filter context** refers to filtering that is applied to a data model **before the evaluation of a DAX** expression begins. It determines which subset of data is used in the calculation. Filter context narrows down the data before a calculation is performed. It's dynamic and changes based on user interactions and formula definitions.
##### Example:

Imagine you have a sales dataset with the following tables:

•       **Sales:** Contains sales transactions with columns like Sales Amount, Product, Region, and Date.

•       **Products:** Contains product information, including a Category column.

**Objective:** We want to calculate the total sales for a specific product category, regardless of any other filters applied in the report.

Total Sales for Category = CALCULATE( SUM(Sales[Sales Amount]), Products[Category] = "Electronics" )

•       **Without CALCULATE:** If you simply used SUM(Sales[Sales Amount]), the measure would be affected by any existing filters in your report (like a region slicer or a date filter).

•       **With CALCULATE:** CALCULATE temporarily changes the filter context.

•       It _removes_ any existing filters that conflict with Products[Category] = "Electronics".

•       It _adds_ the filter Products[Category] = "Electronics".

•       The SUM(Sales[Sales Amount]) is then calculated within this modified filter context.

![[Pasted image 20261012165308.png]]

# 3.3 Chart types

When creating a data visualization, selecting the right chart is crucial for effectively communicating insights. Consider the following factors: 

- Then, **which type of data is being visualized, categorical or numerical?**

	- **Categorical Data:** Charts such as bar charts, pie charts, and column charts.
    
	- **Numerical Data:** Charts such as line charts, scatter plots, box plots, and histograms.

- Finally, **what type of analysis have you performed, exploratory or confirmatory?**

	- **Exploratory Analysis:** Used for discovering patterns and trends (e.g., scatter plots, box plots).
    
	- **Confirmatory Analysis:** Used for validating hypotheses and making decisions (e.g., bar charts, statistical charts).

### **Dimensions vs. Measures**

Dimensions are **qualitative data** that help categorize, group, or segment your data. They do **not** involve numbers that can be aggregated but instead provide **context** for analysis.
-  **Customer Name** tells us who made the purchase.
    
- **Product Category** helps us group items into meaningful categories.
    
- **Order Date** allows us to segment data over time.

Measures, on the other hand, are **quantitative data** that can be aggregated and measured.
- **Sales Revenue** represents the total income from sales.
    
- **Quantity Sold** tells us the number of units purchased.
    
- **Profit Margin** helps us analyze profitability.

## Tables and Matrices

A **Table** in Power BI is a simple way to display data where values are arranged in **columns**, and the data is listed row by row. Each column represents a field, and each row represents a record.

![[Pasted image 20261014125605.png]]

A **Matrix** expands on the concept of a table by allowing us to display data across multiple dimensions. Unlike tables, which only have columns, matrices can show both **rows and columns of values**.

![[Pasted image 20261014125623.png]]

## Charts for Visualizing Data

#### Categorical data charts
![[Pasted image 20261014125902.png]]![[Pasted image 20261014125920.png]]![[Pasted image 20261014130034.png]]![[Pasted image 20261014130200.png]]![[Pasted image 20261014130212.png]]![[Pasted image 20261014130222.png]]

#### Numerical data charts

![[Pasted image 20261014130311.png]]![[Pasted image 20261014130318.png]]
![[Pasted image 20261014130327.png]]
![[Pasted image 20261014130337.png]]

#### Other charts

![[Pasted image 20261014130402.png]]
![[Pasted image 20261014130411.png]]
![[Pasted image 20261014130420.png]]

![[Pasted image 20261014130431.png]]

### Summary charts
![[Pasted image 20261014130503.png]]

Use bar charts for comparing quantities across categories. Use line charts for showing trends over time.

Use pie charts to show proportions. Use scatter plots to display relationships between variables
# 3.4 Data Visualization Best Practices
## Deceptive Charts

### Truncated Y-Axis

**Problem:** A bar chart with a y-axis starting at another value instead of 0 makes small differences appear large.  
**Example:** The figure compares the **average price by category.** The chart on the left, with a **truncated y-axis,** exaggerates the differences between categories, making the gap between Electronics, Furniture, and Stationery appear much larger than it actually is. In contrast, the chart on the right, with a **full y-axis starting from zero,** presents the same differences more accurately, avoiding the illusion of a greater disparity.
![[Pasted image 20261014130624.png]]
**Solution**: Always start bar chart axes at zero to maintain proportional accuracy.

### Unnecessary 3D and embellishments

**Problem**: 3D effects can distort the perception of values.  
**Example:** A 3D pie chart makes some slices appear larger due to perspective, even if they represent the same percentage. In the left chart, the Furniture category looks disproportionately larger due to the 3D effect, even though the actual proportions are consistent. In contrast, the 2D pie chart on the right accurately represents the true size relationships between Electronics, Furniture, and Stationery without distortion.
![[Pasted image 20261014130710.png]]
**Solution**: Use simple, flat designs to ensure clarity.

### Manipulating dual axes

**Problem**: Dual-axis charts can make unrelated data sets appear correlated by manipulating scale ranges. This can mislead viewers into believing a cause-and-effect relationship exists when it does not.

**Example**: A graph showing **phone usage (left y-axis)** and **internet usage (right y-axis)** might be adjusted to make their trends appear identical. This could falsely suggest that increased phone usage directly causes higher internet usage, when in reality, both may be rising due to **technological advancements and accessibility** rather than one influencing the other. If the scales are manipulated, the two lines may look highly correlated even if they aren’t. Viewers might assume that one variable directly drives changes in the other.
![[Pasted image 20261014130827.png]]
**Solution**:
- Use dual axes **only** when comparing **related** data sets, such as revenue and profit margins.
    
- Clearly label both axes and ensure the scale is appropriate.
    
- If the relationship isn’t direct, consider using **separate charts** instead of a dual-axis graph.

### Misleading reversed x axis
**Problem**: Reversing the x-axis direction can mislead viewers by flipping the natural relationship between variables.

**Example**: A chart comparing **GDP (Y-axis)** and **male life expectancy (X-axis)**, but with life expectancy decreasing from left to right, may confuse viewers. Normally, higher GDP is associated with longer life expectancy, but a reversed x-axis might make it seem like lower life expectancy is linked to higher GDP.
![[Pasted image 20261014130917.png]]
**Solution**: Always maintain a standard left-to-right progression for numerical or time-based data to ensure clear and accurate interpretation.

## Key Principles for Effective Data Visualization

### Chart Goal

Cole Nussbaumer Knaflic, the author of Storytelling with Data: A Data Visualization Guide for Business Professionals, asserts that there are two types of charts, exploratory and explanatory.

**Exploratory** charts present data and let the people who view the chart draw their own conclusions.

**Explanatory** charts present a focused message, and insight extracted from or backed up by the data, to make a point.

![[Pasted image 20261014131647.png]]