### Question 1
You are working with a database table that contains data about playlists for different types of digital media. 
The table includes columns for playlist_id and name. 
You want to remove duplicate entries for playlist names and sort the results by playlist ID. 
```
SELECT 
 DISTINCT name
FROM
 playlist
ORDER BY
 playlist_id;
```

### Question 2
You are working with a database table that contains data about music albums. 
The table includes columns for album_id, title, and artist_id. 
You want to check for album titles that are less than 4 characters long. 
```
SELECT *
FROM album
WHERE
 LENGTH(title) < 4;
```
### Question 3
You are working with a database table that contains customer data. 
The table includes columns about customer location such as city, state, and country. 
You want to retrieve the first 3 letters of each country name and use the AS command to store the result in a new column called new_country. 
```
SELECT 
 customer_id,
 SUBSTR(country,1,3) AS new_country
FROM
 customer
ORDER BY
 country;
```

### Question 4
You are working with a database table that contains customer data. 
The table includes columns about customer location such as city, state, and country. The state names are abbreviated. 
You want to retrieve the first 2 letters of each state name and store the result in a new column as new_state. 
```
SELECT
customer_id,
SUBSTR(state,1,2) AS new_state
FROM
customer
ORDER BY
state DESC;
```

### Question 5
You are working on an international project and need to invoice your customers for the work you complete. 
The database you use contains an invoices table. The invoices table contains the following columns: InvoiceId, CustomerId, InvoiceDate, BillingAddress, BillingCity, BillingState, BillingCountry, BillingPostalCode, Total.

Create a query to return all the columns from this table for only customers in Germany who have an invoice total greater than $5. 
```
SELECT *
FROM invoices
WHERE BillingCountry = 'Germany'
AND Total > 5;
```
### Question 5
You are working with a database table that contains customer data. 
The country column designates the country where each customer is located. You want to find out which customers are located in Brazil. 

You write the SQL query that will return only customers located in Brazil. 
```
SELECT *
FROM customer
WHERE country = 'Brazil';
```
