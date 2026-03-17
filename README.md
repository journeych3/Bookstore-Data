# Bookstore-Data

## Project Overview: 
This project analyzes transactional data from an online bookstore to identify patterns in book sales, customer purchasing behavior, and revenue distribution across genres. Using SQL, the dataset was structured into relational tables and analyzed through joins and aggregations to answer key business questions about sales performance.

The goal of this project is to demonstrate practical SQL skills such as:
 - Joining multiple tables
 - Aggregating sales data
 - Identifying top-performing products
 - Analyzing customer and geographic trends

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
The top selling books are "Realigned multitasking" with 28 copies sold and "Implemented encomoassing conglomeration" with 27 copies sold. The sales are evenly distribituted, with the next top sellings books selling 24 and 23 copies. This indicates that the demand is consistent across the books.

The top selling genre is indicated to be mystery, with science fiction, fantasy, and romance falling closely behind. This helps the bookstore to know which books are more popular and indicates what type of boooks the customers are interested in. 

The monthly revenue demonstrates a fluctuating trend with clear peaks and drops. The spikes in revenue represent when demand is particuarly high, while the dips indicate with the demand is particularly low. Understanding these patterns in revenue can help to optimize marketing strategy for the seller and better anticipate consumer patterns. 

The highest spender is is Kim Turner, followed by Jonathon Strickland and Carrie Perez. By identifying and engaging with the customers who have shown to be loyal to the store, the company can curate personalized offers and rewards programs to show appreciation for said customers.  
