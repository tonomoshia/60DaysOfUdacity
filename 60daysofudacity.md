# 60 Days of Udacity

1. What did I learn today?

2. What will I learn tomorrow?

3. What issues are blocking my progress?

## Course Details

- [Business Analytics NanoDegree](https://www.udacity.com/course/business-analytics-nanodegree--nd098)
- [Google Site](https://sites.google.com/udacity.com/bertelsmann-phase-2/home?authuser=0) for our  cohort of the [Bertelsmann Technology scholarship](https://www.udacity.com/bertelsmann-tech-scholarships)
- Key Program Dates for Phase 2: March 2, 2022 thru August 31, 2022
  - [x] Project 1 due March 20, 2022 ([passed](20220311_Udacity_Project1_Review.pdf) March 11, 2022)
  - [ ] Project 2 due May 27, 2022
  - [ ] Project 3 due August 3, 2022
  - [ ] Project 4 due August 31, 2022

## Resources

- [Stats Gist List: An Irreverent Statistician’s Guide to Jargon](https://towardsdatascience.com/stats-gist-list-an-irreverent-statisticians-guide-to-jargon-be8173df090d)
- [Kaggle New York Stock Exchange Data](https://www.kaggle.com/dgawlik/nyse)
- [Viz of the Day](https://public.tableau.com/app/discover/viz-of-the-day)

### Day 1 - 03.08.22

1. Worked on and turned in Project 1.

2. Since my progress from the Challenge course didn’t transfer over, I will start reviewing it to see what’s new.

3. Nothing at this time. Good to go.

### Day 2 - 03.11.22

1. I read the review I received of my first project, worked on it and resubmitted. Starting going through the First section which we already did in the challenge course as my progress did not transfer over. Perused Project 2, read the rubric and downloaded the project files.

2. Tomorrow I will look into the project files and go through the quiz to familiarize myself with the data set. Also read up about making the dashboard as I really did not understand that that well in the Challenge course. The videos were not helpful.

3. Blocker - not understanding the dashboard procedure and how to create ‘scenarios’.

### Day 3 - 03.14.22

1. Watch 30 minutes of [SQL Tutorial - Full Database Course for Beginners](https://youtu.be/HXV3zeQKqGY) from [FreeCodeCamp](https://www.freecodecamp.org).
2. Figure out Index & Match (!!)
3. Time, procrastination and motivation. I see so many people having trouble with Project 2 and I feel like I am going to have an even more difficult time. Kinda avoiding it.

### Day 4 - 03.16.22

1. Started Using SQL for Data Analysis -
   1. Completed Lesson 1: Intro to Using SQL for Data Analytics.
   2. Started Lesson 2: Basic SQL (up to section 7).
2. Continue Lesson 2: Basic SQL.
3. None. Will do Project 2 later.

### Day 5 - 03.22.22

1. Continues Lesson 2: Basic SQL (up to section 22). Had to use Google Chrome to get workspaces working. Safari has cookies blocked and whatnot and I did not want to change that.
2. Continue Lesson 2: Basic SQL.
3. Procrastination, my old friend.

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

- > (greater than)
- < (less than)
- >= (greater than or equal to)
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

Practice Question: Using WHERE with Non-Numeric Data
Filter the accounts table to include the company name, website, and the primary point of contact (primary_poc) just for the Exxon Mobil company in the accounts table.

```sql
SELECT name, website, primary_poc
FROM accounts
WHERE name = 'Exxon Mobil';
```
