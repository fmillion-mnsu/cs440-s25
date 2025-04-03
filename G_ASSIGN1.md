# Group Assignment 1 - Indexing

In this assignment you will take your data scenarios and add optimal **indexes** for your scenarios to the database. You will be able to test the efficacy of your indexes using the Explain tool.

## Requirements

1. **In your groups**, look over your queries and identify and create at least one **index** for each query that would help run the query you created in less time. 

> It is permitted - and encouraged - to look for "overlap" - indexes that would satisfy more than one of your queries! However, you should still be seeking the *optimal* performance - an index that maximizes performance for one query but only marginally helps another is a clue that you should still consider another idnex for the second query.

2. Use MongoDB Compass to create the indexes in the appropriate collections on your team's database server. This is also where you can use Explain to test your queries to see if they run faster.

    > A very important thing to strive for is to avoid `COLLSCAN`s wherever possible. Remember that a `COLLSCAN` requires the database engine to read the *entire* database file - even data it doesn't care about - since the size of documents is not fixed. Even though MongoDB does maintain an index based on the mandatory primary key, this still will not prevent MongoDB from having to actually read every document into memory, parse the JSON data and decide if it is relevant to the query.

You do not need to write any reports for this project. I will compare the indexes on your team's server with the queries each of your team members submitted for Individual Assignment 1. 

## Submission

There is no submission for this project. Create your indexes on the MongoDB server assigned to your project prior to the deadline.

This project is due on April 13th, 2025 at 11:59 PM.
