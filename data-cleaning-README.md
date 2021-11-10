# Automobile Data cleaning practice
SQL data cleaning practice for Google Data Analytics Professional Certificate on Coursera
### Step 1: Inspect colums
According to the data’s description, the *fuel_type* column should only have two unique string values: diesel and gas. Check and make sure that’s true
```
SELECT
  DISTINCT fuel_type
FROM
  cars.car_info;
```
The length column should contain numeric measurements of the cars. So you will check that the minimum and maximum lengths in the dataset align with the data description, which states that the lengths in this column should range from 141.1 to 208.1.
```
SELECT
MIN(length) AS min_length,
MAX(length) AS max_length
FROM
  cars.car_info;
```
### Step 2: Fill in missing data
```
SELECT *
FROM cars.car_info 
WHERE num_of_doors IS NULL;

UPDATE
  cars.car_info
SET
  num_of_doors = "four"
WHERE
  make = "dodge"
  AND fuel_type = "gas"
  AND body_style = "sedan";

UPDATE 
 cars.car_info
SET
 num_of_doors = 'four'
WHERE 
 make = 'mazda'
 AND fuel_type = 'diesel'
 AND body_style = 'sedan';
 ```
 
### Step 3: Identify potential errors
 ```
SELECT
  DISTINCT num_of_cylinders
FROM
  cars.car_info;
```
Found misspelled error.

```
UPDATE
  cars.car_info
SET
  num_of_cylinders = "two"
WHERE
  num_of_cylinders = "tow";
```
According to the data description, the *compression_ratio* column values should range from 7 to 23. Just like when you checked the length values , you can use MIN and MAX to check if that’s correct
```
SELECT
  MIN(compression_ratio) AS min_compression_ratio,
  MAX(compression_ratio) AS max_compression_ratio
FROM
  cars.car_info;
```
Found max compression rate is 70 instead of 23 as the data description shows. After confirming 70 is an error, check number of rows that contain this mistake.

```
SELECT
 COUNT(*) AS number_of_row_delet
FROM 
 cars.car_info
WHERE compression_ratio = 70;
```
After confirm only one row contain this error, it can be deleted.

```
DELETE cars.car_info
WHERE compression_ratio = 70;
```

### Step 4: Ensure consistency
Check the drive_wheels column for inconsistencies
```
SELECT
  DISTINCT drive_wheels
FROM
  cars.car_info;
```
*4wd* show up twice in the results, meaning that one of it contains a space and shoule be trimmed.
```
SELECT
  DISTINCT drive_wheels,
  LENGTH(drive_wheels) AS string_length
FROM
  cars.car_info;
```
```
UPDATE
  cars.car_info
SET
  drive_wheels = TRIM(drive_wheels)
WHERE TRUE;
```

What is the maximum value in the price column of the car_info table? 
```
SELECT 
 max(price)
FROM 
 cars.car_info;
```
