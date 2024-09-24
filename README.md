# Product Recommendation System for E-commerce Project

## Project Background
This project focuses on enhancing product recommendations and understanding market trends for an online retail platform. A **SQL**-based data warehouse was designed to store and manage customer and sales data. The project involved analyzing 10,000 customer records, forecasting sales trends, and building personalized recommendation systems using **Python** to improve user experience. These insights help businesses identify profitable segments and optimize marketing efforts, leading to growth and increased customer satisfaction.

## Dataset Structure 
The dataset for this project was organized into a SQL-based data warehouse with multiple tables for customer data, sales records, product information, and regional market data. The primary data structure used for this analysis and modeling is the combination of two major sources:

  * [Superstore Data](https://github.com/nikitaprasad21/Product-Recommendation-Analysis-Project/blob/main/data/Superstore-Data.csv): Superstore purchase history and revenue data.
  * [Superstore Reviews Data](https://github.com/nikitaprasad21/Product-Recommendation-Analysis-Project/blob/main/data/Superstore-Dataset-Reviews.csv): Rating, review and summary of the product given by the customer. 
    
Note: The dataset comprised 10,000+ records, divided into 36 columns, the feature-target description you can see [here](https://github.com/nikitaprasad21/Product-Recommendation-Analysis-Project/blob/main/data/Features_Target_Description.txt).


## Executive Summary
This project implemented a SQL-based Superstore Data Warehouse and developed product recommendation models to improve customer experience and sales strategies. By analyzing data from 10,000 customers, the system identified profitable market segments, forecasted sales trends, and provided personalized product recommendations. 

Key insights included the dominance of the "Consumer" segment in profitability, the significant role of California as the top-performing market, and strategies for improvement in underperforming regions such as North Dakota.


## Codes
* The targed **SQL queries** regarding various business questions can be found [here](https://github.com/nikitaprasad21/Product-Recommendation-Analysis-Project/blob/main/notebooks/Products-Analysis.sql).
* The interactive **Tableau dashboard** used to report and explore sales trends can be found [here](https://public.tableau.com/app/profile/nikita.prasad/viz/QuarterlySalesForecastingAnalysisDahboard/AnalysisDashboard).
* The **Python Pipeline** used for EDA, Model Building for Recommendation Systems and Deployment of model can be found [here](https://github.com/nikitaprasad21/Product-Recommendation-Analysis-Project/blob/main/notebooks/Product-Recommendation-Project.ipynb).
* The **Recommendation App** demo can be found [here](https://huggingface.co/spaces/nikitaprasad-analyst/product-recommendation-system).

## Dashboard

Here is the glimpse of dashboard.
![Screenshot 2023-04-12 165416](https://user-images.githubusercontent.com/84131752/231447810-39810cfc-f423-4463-b6c8-e2eb4c73f878.png)


## Insights

#### Category 1: Profitable Market Segment
   * The "Consumer" category is the most profitable customer segment among our customer segments, generating the highest revenue and profit, highlighting its significance to our business.

#### Category 2: Top Performing Region
   * California emerged as the largest and most profitable market, contributing significantly to total sales.
#### Category 3: Underperforming Markets
   * North Dakota represents an underperforming market, requiring strategic attention to improve profitability and market share.
#### Category 4: Growth Forecast
   * The sales forecast predicts increased sales in Q4 of 2018, presenting growth opportunities for targeted marketing efforts.

## Recommendations

#### Category 1: Capitalize on Growth Opportunities:

   * With the anticipated growth in Quarterly Sales Forecasting for 2018 Q4, it is advisable to allocate additional additional marketing resources to maximize sales opportunities during this period.

#### Category 2: Focus on the "Consumer" Category:
   * Develop targeted marketing campaigns, personalized promotions, and enhanced customer experiences to further boost profitability within the "Consumer" segment  segment.

#### Category 3. Optimize Market Strategies:
   * As California is the most profitable market, it is essential to continue investing in this region through focused marketing efforts, maintaining customer loyalty, and increasing market share.
     
#### Category 4. Improve Underperforming Markets:

   * Conduct in-depth market research in North Dakota to understand consumer behavior and tailor marketing efforts to boost sales and profitability in the region.

## Assumptions and Caveats
#### Assumptions:

* The data provided for analysis is accurate and reflects customer preferences and purchasing patterns.
* The sales forecast is based on historical trends and assumes no major disruptions in market behavior.
#### Caveats:

* Seasonal fluctuations and external factors like economic changes or unforeseen events may impact sales trends and market behavior, making forecast predictions less accurate.
* The recommendation models are built on available data; their effectiveness may vary if customer preferences shift or if there is insufficient data for new products.
