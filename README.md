# Superstore dashboard Analysis
## Dashboard Link: 
# Problem Statement : 
This Dashboard helps the store owner to understand their sales mechanism. It helps them to understand the performers of every product in their inventory and also how customers engage with the products. It helps one to understand which category and segment performs better than the others and possibly why?. It helps the company to identify the State and City with the most Orders per certain period as well as the respective  customers emanating from those locations. Hence , using this dashboard they can easily make an evaluation on how to uncover the factors responsible for the differences in sales in terms of locations and customers and therefore take the necessary steps for better productivity.
From the analysis, it’s interesting to know that the Technology category has the most orders in which ‘Phones’ as a subcategory has the highest sales followed by Chairs.
It’s also interesting to know that California State has the most amount orders followed by New York 
It’s also good to know that 2022 has the highest sales rate compared to the previous 3 years which is a good insight to take note in order to even have better robust sales record come next year. 
### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.
- step 5 : A separate table was created by extraction from the main table using the Value function in which the following Dax function was used: distinctCustomers = VALUES(superstore_dataset[customer])
 
- step 6 : A decomposition tree was used to be able to give a breakdown on the order of distribution across the category & subcategory of items as well as the locations.
- step 7 : a map visual used to illustrate some_of_sales by State .
 
- Step 8 : Visual (Slicers) were added for two fields named "category", "State".
- Step 9 : Four card visuals were added to the canvas, one representing ‘Total_orders’, ‘overall_customers’, ‘total_profit’, and lastly ‘Total_sales’.
- step 10 : Some couple of bar chart were also added in which one represent Total_orders by state, some of sales by product_name, total_orders by state, total_orders by segments, some of sales by subcategory, total_sales by customer.
- step 11 : A Funnel was also added to showcase the Total_orders by category
- step 12 : A pie chart was also added to showcase Total_sales and sum of profit by category
- step 13 : A measure was created to calculate the total_orders and the following Dax measure was used: Total_orders = COUNT(superstore_dataset[order_id])
A card visual was used to represent the Total_orders : 

- step 14 : Another measure was used to calculate the over_all customers and the following Dax measure was used : Overall-customers = DISTINCTCOUNT(superstore_dataset[customer])
A card visual was used to illustrate the expression: 
- step 15 : Two additional  measures were used to calculate the Total_profit and Total_sales across four year periods and the following Dax measure was used respectively : Total_profit = SUM(superstore_dataset[profit])
Total_sales = SUM(superstore_dataset[sales]).
A card visual was used to represent them :

- step 16 : A line chart was used to illustrate the total_sales by year in which it shows an increasing order of growth in sales.
- step 17 : A line also was used to illustrate the total sales by order_18 : date in which a date hierarchy was used.
- step 18 : Another measure was created to show the Top_product in terms of orders whereby the following Dax measure was used: TopProduct = 
CALCULATE(
    VALUES('superstore_dataset'[product_name]),
    FILTER(
        'superstore_dataset',
        [OrdersPerProduct] = MAXX(ALL('superstore_dataset'[product_name]), [OrdersPerProduct])
    )
)

A card visual was used to represent this Top_product :

# report snapshot    (power bi Desktop)
![powerbiDesktopPreview](https://github.com/Eelmukhty/Superstore-Analysis/assets/170774661/a27f222d-8c05-47a0-b5cd-5df6fea38084)



# Insights 
Following inferences can be drawn from the dashboard
## [1] Total orders = 10k
   [2] Over all distinct customers across the four period = 793
   [3] Total sales = 2.30M
   [4] Total profit = 286.40k
## As regards to orders, it appears that state of California has the most number of orders while Wyoming has the least number of orders 
## Technological items are the most sold items across the four  year period accounting for about 32.36% followed by Furniture with 28.73%  and lastly office supplies with 27.83%
## Phones are the most sold items across the period, thus effort should be made in order to maintain the growth

    










