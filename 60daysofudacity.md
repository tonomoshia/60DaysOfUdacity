# 60 Days of Udacity

1. What did I learn today?

2. What will I learn tomorrow?

3. What issues are blocking my progress?

## Course Details

- [Business Analytics NanoDegree][1]
- [Google Site][2] for our  cohort of the [Bertelsmann Technology scholarship][3]
- Key Program Dates for Phase 2: March 2, 2022 thru August 31, 2022
  - [x] Project 1 due March 20, 2022 ([passed](20220311_Udacity_Project1_Review.pdf) March 11, 2022)
  - [ ] Project 2 due May 27, 2022
  - [ ] Project 3 due August 3, 2022
  - [ ] Project 4 due August 31, 2022

## Resources

- [Stats Gist List: An Irreverent Statistician’s Guide to Jargon][4]
- [Kaggle New York Stock Exchange Data][5]
- [Viz of the Day][6]

## Days
---------

### Day 1 - 03.08.22

1. Worked on and turned in Project 1.
2. Since my progress from the Challenge course didn’t transfer over, I will start reviewing it to see what’s new.
3. Nothing at this time. Good to go.

---------

### Day 2 - 03.11.22

1. I read the review I received of my first project, worked on it and resubmitted. Starting going through the First section which we already did in the challenge course as my progress did not transfer over. Perused Project 2, read the rubric and downloaded the project files.

2. Tomorrow I will look into the project files and go through the quiz to familiarize myself with the data set. Also read up about making the dashboard as I really did not understand that that well in the Challenge course. The videos were not helpful.

3. Blocker - not understanding the dashboard procedure and how to create ‘scenarios’.

---------

### Day 3 - 03.14.22

1. Watch 30 minutes of [SQL Tutorial - Full Database Course for Beginners][7] from [FreeCodeCamp][8].
2. Figure out Index & Match (!!)
3. Time, procrastination and motivation. I see so many people having trouble with Project 2 and I feel like I am going to have an even more difficult time. Kinda avoiding it.

---------

### Day 4 - 03.16.22

1. Started Using SQL for Data Analysis -
   1. Completed Lesson 1: Intro to Using SQL for Data Analytics.
   2. Started Lesson 2: Basic SQL (up to section 7).
2. Continue Lesson 2: Basic SQL.
3. None. Will do Project 2 later.

---------

### Day 5 - 03.22.22

1. Continues Lesson 2: Basic SQL (up to section 22). Had to use Google Chrome to get workspaces working. Safari has cookies blocked and whatnot and I did not want to change that.
2. Continue Lesson 2: Basic SQL.
3. Procrastination, my old friend.

---------

*Notes*
------

   ```sql
   SELECT occurred_at, account_id, channel
    FROM web_events
    LIMIT 15;
   ```

to get orders in order of date, earliest to latest (default order)

```sql
    SELECT *
     FROM orders
     ORDER BY occurred_at
     LIMIT 1000;
```

to get them in decending order (most recent first)

```sql
    SELECT *
    FROM orders
    ORDER BY occurred_at DESC
    LIMIT 1000;
```

Write a query to return the 10 earliest orders in the orders table. Include the id, occurred_at, and total_amt_usd.

```sql
    SELECT id, occurred_at, total_amt_usd
    FROM orders
    ORDER BY occurred_at
    LIMIT 10;
```

Write a query to return the top 5 orders in terms of the largest total_amt_usd. Include the id, account_id, and total_amt_usd.

```sql
    SELECT id, occurred_at, total_amt_usd
    FROM orders
    ORDER BY total_amt_usd DESC
    LIMIT 5;
```

Write a query to return the lowest 20 orders in terms of the smallest total_amt_usd. Include the id, account_id, and total_amt_usd.

```sql
    SELECT id, occurred_at, total_amt_usd
    FROM orders
    ORDER BY total_amt_usd
    LIMIT 20;
```

This query selected account_id and total_amt_usd from the orders table, and orders the results first by total_amt_usd in descending order and then account_id

```sql
    SELECT  account_id,
        total_amt_usd
  FROM orders
  ORDER By total_amt_usd DESC, account_id
```

Write a query that displays the order ID, account ID, and total dollar amount for all the orders, sorted first by the account ID (in ascending order), and then by the total dollar amount (in descending order).

```sql
    SELECT id, account_id, total_amt_usd
    FROM orders
    ORDER BY account_id, total_amt_usd DESC;
```

Now write a query that again displays order ID, account ID, and total dollar amount for each order, but this time sorted first by total dollar amount (in descending order), and then by account ID (in ascending order).

```sql
    SELECT id, account_id, total_amt_usd
    FROM orders
    ORDER BY total_amt_usd DESC, account_id;
```

Compare the results of these two queries above. How are the results different when you switch the column you sort on first?

```
The last query has biggest orders on top. The original query has the orders grouped by account Id and then sored by amount.
```
---------

### Day 6 - 03.24.22

1. Continues Lesson 2: Basic SQL (up to section 29).
2. Continue Lesson 2: Basic SQL.
3. Procrastination and distraction

*Notes*
------

WHERE clause filters results
```Using the WHERE statement, we can display subsets of tables based on conditions that must be met. You can also think of the WHERE command as filtering the data.```

```sql
SELECT *
FROM orders
WHERE account_id = 4251
ORDER BY occurred_at
LIMIT 1000;
```

Common symbols used in WHERE statements include:

- < (less than)
- *> (greater than)*
- *>= (greater than or equal to)*
- <= (less than or equal to)
- = (equal to)
- != (not equal to)

*Questions*
Write a query that:

Pulls the first 5 rows and all columns from the orders table that have a dollar amount of gloss_amt_usd greater than or equal to 1000.

```sql
SELECT *
FROM orders
WHERE gloss_amt_usd >= 1000
LIMIT 5;
```

Pulls the first 10 rows and all columns from the orders table that have a total_amt_usd less than 500.

```sql
SELECT *
FROM orders
WHERE total_amt_usd <500
LIMIT 10;
```

You will notice when using these WHERE statements, we do not need to ORDER BY unless we want to actually order our data. Our condition will work without having to do any sorting of the data.

The WHERE statement can also be used with non-numeric data. We can use the = and != operators here. You need to be sure to use single quotes (just be careful if you have quotes in the original text) with the text data, not double quotes.

Commonly when we are using WHERE with non-numeric data fields, we use the LIKE, NOT, or IN operators.

*Practice Question:* Using WHERE with Non-Numeric Data
Filter the accounts table to include the company name, website, and the primary point of contact (primary_poc) just for the Exxon Mobil company in the accounts table.

```sql
SELECT name, website, primary_poc
FROM accounts
WHERE name = 'Exxon Mobil';
```
--------- 

### Day 7 - 03.29.2022

1. Continue Lesson 2: Basic SQL (up to section 30) not very far
2. Continue Lesson 2
3. Time.

*Notes*

#### Arithmetic Operators

#### Derived Columns

Creating a new column that is a combination of existing columns is known as a **derived** column (or "calculated" or "computed" column). Usually, you want to give a name, or "alias," to your new column using the **AS** keyword.

This derived column, and its alias, are generally only temporary, existing just for the duration of your query. The next time you run a query and access this table, the new column will not be there.

If you are deriving the new column from existing columns using a mathematical expression, then these familiar mathematical operators will be useful:

1. `*` (Multiplication)
2. `+` (Addition)
3. `-` (Subtraction)
4. `/` (Division)

Consider this example:

```sql
SELECT id, (standard_amt_usd/total_amt_usd)*100 AS std_percent, total_amt_usd
FROM orders
LIMIT 10;
```

Here we divide the standard paper dollar amount by the total order amount to find the standard paper percent for the order, and use the **AS** keyword to name this new column "std_percent." You can run this query on the next page if you'd like, to see the output.

#### Order of Operations

Remember PEMDAS from math class to help remember the order of operations? If not, check out this [link](http://www.purplemath.com/modules/orderops.htm) as a reminder. The same order of operations applies when using arithmetic operators in SQL.

The following two statements have very different end results:

1. **Standard_qty / standard_qty + gloss_qty + poster_qty**
2. **standard_qty / (standard_qty + gloss_qty + poster_qty)**

It is likely that you mean to do the calculation as written in statement number 2!

##### Code from the Video

```sql
SELECT account_id,
       occurred_at,
       standard_qty,
       gloss_qty + poster_qty AS nonstandard_qty
FROM orders;
```

#### Questions using Arithmetic Operations

Using the **orders** table:

1. Create a column that divides the `standard_amt_usd` by the `standard_qty` to find the unit price for standard paper for each order. Limit the results to the first 10 orders, and include the `id` and `account_id` fields.

   ```sql
SELECT id, account_id, standard_amt_usd / standard_qty AS standard_paper_unit_price
FROM orders
LIMIT 10;
   ```

Continued the second question on another day.

---------
### Day 8 - 04.02.22

1. Watch 15 minutes of [SQL Tutorial - Full Database Course for Beginners][7] from [FreeCodeCamp][8]. Continue Lesson 2: Basic SQL (up to section 41)
2. Finish Lesson 2: Basic SQL and start Lesson 3: SQL Joins
3. Getting started, not being distracted.

*Notes*

#### Questions using Arithmetic Operations (continued from day 7)

2. Write a query that finds the percentage of revenue that comes from poster paper for each order. You will need to use only the columns that end with `_usd`. (Try to do this without using the `total` column.) Display the `id` and `account_id` fields also. **NOTE - you will receive an error with the correct solution to this question. This occurs because at least one of the values in the data creates a division by zero in your formula. There are ways to better handle this. For now, you can just limit your calculations to the first 10 orders, as we did in question #1, and you'll avoid that set of data that causes the problem.**

```sql
SELECT id, account_id,
(poster_amt_usd *100)/(standard_amt_usd + gloss_amt_usd + poster_amt_usd) AS poster_percent
FROM orders
LIMIT 10;
```

#### Introduction to Logical Operators

Logical Operators include:

**LIKE** This allows you to perform operations similar to using **WHERE** and =, but for cases when you might not know exactly what you are looking for.
**IN** This allows you to perform operations similar to using WHERE and =, but for more than one condition.
**NOT** This is used with **IN** and **LIKE** to select all of the rows **NOT LIKE** or **NOT IN** a certain condition.
**AND & BETWEEN** These allow you to combine operations where all combined conditions must be true.
**OR** This allows you to combine operations where at least one of the combined conditions must be true.

[**LIKE** video][9]

```sql
SELECT *
FROM accounts
WHERE website LIKE '%google%';
```

The **LIKE** operator is extremely useful for working with text. You will use ** LIKE**  within a ** WHERE**  clause. The LIKE operator is frequently used with %. The % tells us that we might want any number of characters leading up to a particular set of characters or following a certain set of characters, as we saw with the google syntax above. 

Remember you will need to use single quotes for the text you pass to the LIKE operator because these lower and uppercase letters are not the same within the string. Searching for 'T' is not the same as searching for 't'. In other SQL environments (outside the classroom), you can use either single or double-quotes.

##### Questions using the LIKE operator

Use the accounts table to find

1. All the companies whose names start with 'C'.

```sql
SELECT *
FROM accounts
WHERE name LIKE 'C%';
```

1. All companies whose names contain the string 'one' somewhere in the name.

```sql
SELECT *
FROM accounts
WHERE name LIKE '%one%';
```

3. All companies whose names end with 's'.

```sql
SELECT *
FROM accounts
WHERE name LIKE '%s';
```

[**IN** video][10]

```sql
SELECT *
FROM orders
WHERE account_id IN (1001,1021);
```

The **IN**  operator is useful for working with both numeric and text columns. This operator allows you to use an =, but for more than one item of that particular column. We can check one, two, or many column values for which we want to pull data, but all within the same query. In the upcoming concepts, you will see the **OR**  operator that would also allow us to perform these tasks, but the **IN**  operator is a cleaner way to write these queries.

Expert Tip
In most SQL environments, although not in our Udacity's classroom, you can use single or double quotation marks - and you may NEED to use double quotation marks if you have an apostrophe within the text you are attempting to pull.

In our Udacity SQL workspaces, note you can include an apostrophe by putting two single quotes together. For example, Macy's in our workspace would be 'Macy''s'.

#### Questions using IN operator

1. Use the accounts table to find the account name, primary_poc, and sales_rep_id for Walmart, Target, and Nordstrom.

```sql
SELECT name, primary_poc, sales_rep_id
FROM accounts
WHERE name IN ('Walmart', 'Target', 'Nordstrom')
```

2. Use the web_events table to find all information regarding individuals who were contacted via the channel of organic or adwords.

```sql
SELECT *
FROM web_events
WHERE channel IN ('organic', 'adwords')
```

[**NOT** video][11]

```sql
SELECT sales_rep_id,
       name
FROM accounts
WHERE sales_rep_id NOT IN (321500,321570)
ORDER BY sales_rep_id
```

```sql
SELECT *
FROM accounts
WHERE website NOT LIKE '%com%';
```

The NOT operator is an extremely useful operator for working with the previous two operators we introduced: **IN** and **LIKE**. By specifying **NOT LIKE** or **NOT IN**, we can grab all of the rows that do not meet particular criteria.

##### Questions using the NOT operator

We can pull all of the rows that were excluded from the queries in the previous two concepts with our new operator.

1. Use the accounts table to find the account name, primary poc, and sales rep id for all stores except Walmart, Target, and Nordstrom.

```sql
SELECT name, primary_poc, sales_rep_id
FROM accounts
WHERE name NOT IN ('Walmart', 'Target', 'Nordstrom')
```

2. Use the web_events table to find all information regarding individuals who were contacted via any method except using organic or adwords methods.

```sql
SELECT *
FROM web_events
WHERE channel NOT IN ('organic', 'adwords')
```

3. Use the accounts table to find:
   1. All the companies whose names do not start with 'C'.

```sql
SELECT *
FROM accounts
WHERE name NOT LIKE 'C%';
```

   2. All companies whose names do not contain the string 'one' somewhere in the name.

```sql
SELECT *
FROM accounts
WHERE name NOT LIKE '%one%';
```

   3. All companies whose names do not end with 's'

```sql
SELECT *
FROM accounts
WHERE name NOT LIKE '%s';
```

[1]: https://www.udacity.com/course/business-analytics-nanodegree--nd098
[2]: https://sites.google.com/udacity.com/bertelsmann-phase-2/home?authuser=0
[3]: https://www.udacity.com/bertelsmann-tech-scholarships
[4]: https://towardsdatascience.com/stats-gist-list-an-irreverent-statisticians-guide-to-jargon-be8173df090d>
[5]: https://www.kaggle.com/dgawlik/nyse
[6]: https://public.tableau.com/app/discover/viz-of-the-day
[7]: https://youtu.be/HXV3zeQKqGY
[8]: https://www.freecodecamp.org
[9]: https://youtu.be/O5z6eWkNip4
[10]: https://youtu.be/_JPO7wwX3uA
[11]: https://youtu.be/dSQF87oW8a0
