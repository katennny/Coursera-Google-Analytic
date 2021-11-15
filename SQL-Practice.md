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

### Question 6
You are working on a project about music and have a table of genres you need to sort. The Genres table contains the columns GenreId and Name.
Write a SQL query to return the name of each genre from this table in alphabetical order.
```
SELECT Name
FROM Genres
ORDER BY Name;
```

### Question 7
You are working on a project about music and have a table of tracks you need to sort.
The database you use contains a Tracks table. The table contains the following columns: TrackId, Name, AlbumId, MediaTypeId, GenreId, Composer, Milliseconds, Bytes, and UnitPrice.
Write a SQL query to pull all columns from the Tracks table for only tracks with Chris Cornell as the composer. Sort the results in descending order by GenreId.
```
SELECT *
FROM Tracks
WHERE Composer = 'Chris Cornell'
ORDER BY GenreId DESC;
```

### Question 8
You are querying a database that contains data about music. Each album is given an ID number. You are only interested in data related to the album with ID number 6. The album IDs are listed in the album_id column. 
You write the SQL query that will return only data about the album with ID number 6.
```
SELECT *
FROM track
WHERE album_id = 6;
```

### Question 9 
You are working with a database that contains invoice data about online music purchases. You are only interested in invoices sent to customers located in the city of Paris. You want to sort the invoices by order total in ascending order. The order totals are listed in the total column. 
You write the SQL query that will sort the invoices by order total in ascending order.
```
SELECT * 
FROM invoice
WHERE billing_city = 'Paris'
ORDER BY total;
```
