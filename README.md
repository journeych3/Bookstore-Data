# Bookstore Sales and Audience Insights Analysis

## Project Overview: 
This project analyzes transactional data from an online bookstore to identify patterns in book sales, reader purchasing behavior, and genre popularity. Using SQL and BigQuery, the dataset was structured into relational tables and analyzed to explore trends that could inform marketing and promotional strategies in the publishing industry. 

The analysis of this project focuses on identifying: 
 - top performing titles
 - genre demand trends
 - customer purchasing behavior
 - seasonal revenue patterns 

## Tools Used: 
- Kaggle
- BigQuery
- Github

## Database
 The database used is a synthetic set that holds book titles and genres, sales records, and customer information.

## Key Questions
The key questions are: 
 - What are the top selling books?
 - What are the top selling genres? 
 - What is the montlhy revenue?
 - Which customers bought the most books? 

## Sample Query
SELECT
  books.Title,
  SUM(orders.Quantity) AS total_quantity_sold
FROM
  `book-store-03112026`.`book_store_data`.`orders` AS orders
INNER JOIN
  `book-store-03112026`.`book_store_data`.`books` AS books
ON
  orders.Book_ID = books.Book_ID
GROUP BY
  books.Book_ID,
  books.Title
ORDER BY
  SUM(orders.Quantity) DESC;
  
## Key Insights 
Several titles emerged as consistent top sellers, with the leading book selling 28 copies. The sales among the top titles were relatively close, indicating the demand is distributed evenly across multiple books rather than a single bestseller. This suggests that targeted marketing campaigns across several high-performing titles could drive stronger overall sales. 

Mystery emerged as the highest performing genre, followed closely by science fiction fantasy, and romance. These results suggest that readers are currently interested in narrative-driven genres, which highlights potential opportunities for targeted marketing campaigns and promotional placements within these categories. 

The monthly revenue demonstrates a fluctuating trend with distinct peaks and declines. Understanding these seasonal patterns could help publishers and retailers strategize when best to time promotions, advertising campaigns, and book launches.

A small group of customers accounted for the highest purchase volume, indicating the presence of highly engaged readers. Identifying and supporting these loyal customers could help bookstores develop targeted marketing strategies such as personalized recomendations, newsletters, or early access promotions.

## Marketing Implications
The insights from this analysis suggest several opportunities for marketing strategy:
- concentrate promotional efforts on high performing genres such as mystery and science fiction
- rather than relying on a bestseller, highlight multiple top-performing titles
- align marketing campaigns with periods of increased reader demand
- engage highly active customers thorugh targeted promotions and recommendations
