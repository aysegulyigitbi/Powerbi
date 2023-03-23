# 👋 Power BI Aggregate Functions — Comparison of SUM and SUMX Functions

Aggregate functions are the backbone of Power BI, one of the most popular tools used for data analysis and reporting. These functions work on a column-by-column basis, require only one parameter, and do not operate on rows. Moreover, they work on a single column and cannot operate on multiple columns simultaneously.

There are several aggregate functions in Power BI, including APPROXIMATEDISTINCTCOUNT, AVERAGE, AVERAGEA, AVERAGEX, COUNT, COUNTA, COUNTAX, COUNTBLANK, COUNTROWS, COUNTX, DISTINCTCOUNT, DISTINCTCOUNTNOBLANK, MAX, MAXA, MAXX, MIN, MINA, MINX, PRODUCT, PRODUCTX, SUM, and SUMX.

The SUM function is a simple addition operation that summarizes a value based on a filter context. It operates on a single column and provides a straightforward way to get the total of a particular set of values. On the other hand, the SUMX function extends the functionality of SUM by allowing calculations to be performed on each row of a specified table, making it ideal for complex scenarios.

In conclusion, while both SUM and SUMX functions are valuable tools in Power BI, they serve different purposes. The SUM function is ideal for simple addition operations on a single column, while the SUMX function is more suitable for complex calculations that require analysis of multiple rows in a table.

SUM(<column>)

SUM is a simple aggregate function. Summarizes a value based on a filter context.

Toplam Satış Tutarı = SUM(‘işlemler’[Satış Tutarı])

![image](https://user-images.githubusercontent.com/127193220/227167194-2e7f69b5-5440-47a5-b35e-0d936f0d3e98.png)

The SUM Function calculates the value summarizing the Total Sales Amount in our table when no filter is selected.

NOTE: All other aggregate functions work in the same way.

SUMX()

SUMX function is another essential iterative function in Power BI. It is called an iterative function because of its iterative nature.

Other iterative functions in Power BI include AverageX, MinX, MAXX, CountaX, and more.

It's important to note that iterative functions loop through all the rows in the input table, storing the expression results in temporary memory. They then apply the summation to the temporary storage results, freeing up memory usage, and displaying the calculation result in a visual format.

For instance, if we want to see the total sales amounts for each of our products based on their sales quantities, the SUMX function will summarize the total sales amounts for each row, storing the results in temporary memory based on their sales quantities. This way, it provides us with a summary of the total sales amounts based on sales quantities for each product.

Satış Adedine Göre Toplam Satış Tutarı = SUMX(‘işlemler’,

‘işlemler’[Satış Adedi]*’işlemler’[Satış Tutarı])

![image](https://user-images.githubusercontent.com/127193220/227167667-1b3de390-701d-43e0-bf57-c347dda77f70.png)

Using the SUMX Function with the FILTER Function

Let's delve into the details of SUMX, a powerful iterative function used in Power BI. Due to its iterative nature, SUMX is classified as an iterative function.

Other iterative functions include AverageX, MinX, MAXX, CountaX, and more.

Note that iterative functions cycle through all rows in the input table and store the result of the expression in temporary memory. Then, they apply summation to the temporary storage results, free up memory usage, and visualize the calculation result.

If we want to see the total sales by sales quantity for each of our products, the SUMX function will summarize the sales amounts for each row after computing all values and store the results in temporary memory. Then, it will provide us with the total sales by sales quantity and free up memory usage.

To use SUMX, we can use the FILTER function as input to provide a calculation result in a filtered dataset. If we want to filter our total sales by sales amount greater than $48,000, we would add the Filter function to the input of the SUMX function. By doing this, we can obtain the new value for our total sales by sales quantity based on the filtered dataset.

Satış Adedine Göre Toplam Satış Tutarı = SUMX(

FILTER(‘işlemler’,

‘işlemler’[Satış Tutarı]>48000),

‘işlemler’[Satış Adedi]*’işlemler’[Satış Tutarı])

![image](https://user-images.githubusercontent.com/127193220/227167886-097de805-ab9e-4e47-8e15-b57704090cab.png)

SUMX is a function in Power BI that allows you to set both an expression and a table as input. This function is an iterative function due to its iterative nature.

Other iterative functions include AverageX, MinX, MAXX, CountaX, and so on.

Note that iterative functions provide a loop over all rows in the input table and store the result of the expression in temporary memory. They then apply a summation to the temporary storage results, release memory usage, and visualize the calculation results.

If we want to see the total sales amounts for each of our products based on the sales quantities, the SUMX function will summarize the total sales amounts based on the sales quantities for each row and store them in temporary memory. In addition, the FILTER function used as input for SUMX only gives us the calculation result in a filtered dataset.

If we want to filter the total sales based on the sales amount of our products, we need to add the Filter function to the input of the SUMX function. In our example, when we create a new metric for products with sales amounts greater than 48,000, we will have obtained the new value of our total sales amount by sales quantity.

In summary, SUM and SUMX are functions that calculate the total. While SUM only summarizes the values of a single column, SUMX is the sum of an expression that can be dynamically calculated from a resolved table.
