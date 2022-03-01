# postgresql_introduction

Here I will be documenting the steps taken in learning ***PostgreSQL (pgAdmin4)***.

## Fundamental SQL Statements

### CREATE TABLE

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_create_table_query.png)

### INSERT

- Without column names:

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_insert_query.png)

- With column names specified:

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_insert_query_column_names.png)

### COPY

- Importing data from a file:

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_copy_query.png)

### SELECT

- Below are three examples of using the **SELECT** statement:
  * SELECT your desired fields
  * SELECT * to return all values
  * SELECT DISTINCT to return unique values

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_select_query.png)

### WHERE

- Showing the **WHERE** clause with different conditions:
  * equals
  * equality operator
  * matching string

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_where_query.png)

### Logical Operators

- **AND**, **OR**, **NOT**:

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_logical_query.png)

### UPDATE

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_update_query.png)

### DELETE

- **DELETE** statement:
  * single-row
  * multiple-rows
  * all rows

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_delete_query.png)

### ALTER

- Various uses of **ALTER**:
  * add column
  * drop column
  * change column data type
  * rename column
  * set column to not allow *null* values
  * drop column that allows *null* values
  * add a constraint to column
  * set a column to being the *Primary Key*

![](https://github.com/latiful-hassan/postgresql_introduction/blob/main/postgresql_introduction_screenshots/psql_alter_query.png)

## Filtering

### IN, BETWEEN & LIKE

- **IN** allows us to check for a value within the data set
- **BETWEEN** checks for values between two contraint values (simplifies query so we do not have to use **OR**)
- **LIKE** uses a **wildcard** which is a placeholder value, in the example the query will return names starting with 'J'

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/psql_filtering_query.png)

## Ordering

### ORDER BY & LIMIT

- **ORDER BY** clauses allows sorting of the returned data set by either ascending or decending
- **LIMIT** is used to put a cap on how many rows are returned 

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/psql_ordering_query.png)

## Aggregate Commands

### COUNT, SUM, AVERAGE, MIN & MAX

- **COUNT** gives us a count of results returned, in the example, the query will return a count of all the orders the customer has and all the different products
- **SUM** aggregates all values
- **AVERAGE** gives an average of values
- **MIN** and **MAX** gives the minimum and maximum values

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/psql_aggregate_query.png)


## Grouping Commands

### GROUP BY & HAVING

- With the **GROUP BY** clause, you can group together one or more columns, for example we can count all the customers and group by buy region 
- We can also combine many aggregations together as seen in the example where we find summarise metrics for each customer and find the top 5 spenders in the customer data set
- The **HAVING** clause can only be used in tandem with **GROUP BY** and it restricts the groups returned (similar to **WHERE**). In the example below we find the regions that have more than 200 customers

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/psql_grouping_commands.png)


## Conditional Statement

### CASE WHEN

- **CASE WHEN** is similar to a traditional **IF** statement where we specify conditions
- Here we are putting different ages into categories or *bins*

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/psql_case_query.png)

## Joins

- Joins allow merging of tables on a condition (predicate) commonly two equal ID values (primary and foreign keys)

### INNER

- Returns only those values that satisfy the join predicate:

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/inner.png)

### LEFT/RIGHT JOIN

- Returns all rwos from left/right table, even without matches:

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/left_right.png)

### FULL OUTER JOIN

- This combines the results of both a left and right join:

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/full_outer.png)

### EXCEPT

- This operator is used to return rows in the first select statement that are not returned by the second:

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/except.png)

## Subqueries

- A **Subquery** is a query within a query, specifically withing the **WHERE**, **FROM** or **SELECT** clauses:
  * for the **WHERE** clause example we find all columns where the customer ID is from customers over the age of 60
  * for the **FROM** clause example we use a subquery to essential craete a table so that we can save resources, otherwise this would have to be done in two queries
  * for the **SELECT** clause example this is the same as using a **LEFT JOIN**

![](https://github.com/latiful-hassan/postgresql_introduction_inprogress/blob/main/postgresql_introduction_screenshots/subqueries.png)
