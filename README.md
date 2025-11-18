## Power BI Movies Exercise
In this exercise, you'll be making use of Power BI to answer questions using multiple data sources.

First, import all 4 tables from the movie_casts database. 

When performing calculations or creating visuals using values from multiple tables, it is often useful to link those tables using [relationships](https://learn.microsoft.com/en-us/power-bi/transform-model/desktop-create-and-manage-relationships). Sometimes relationships can be detected automatically when the data is loaded, but other times you'll have to create them yourself.

Use the "Manage relationships" button to create the following relationships:
* best_actresses <-> people
* best_actors <-> people
* people <-> casts

Next, connect to your local movies database and import the 4 tables from it. You can do this by creating a PostgresSQL database connection and using localhost as the server. Once you have loaded the tables, create relationships between these tables and with the movie_casts tables.

Now that you've gotten your data model set up, use it to complete the following tasks or to answer the following questions:

1. Make a scatterplot for length vs budget where each point in your plot represents a different movie.  Then make each mpaa rating represented by a different color.
2. Which actors have the most Oscar nominations without ever winning? What about actresses? 
3. Have more actors or actresses won multiple awards? Hint: You could use use the Transform Data button to create a new table combinbing the best_actor and best_actress tables and then use this new table to answer this question. See https://learn.microsoft.com/en-us/power-query/append-queries. 
4. Who is the top actor or actress in terms of total profit for movies that they have starred in? (Profit is worldwide gross minus budget.) Hint: You may want to add a [New Quick Measure](https://learn.microsoft.com/en-us/power-bi/transform-model/desktop-quick-measures) to the revenue table. 
5. Who is the top actor or actress in terms of total profit who has not been nominated for an Oscar? Hint: You may want to use the Transform Data button and merge queries to make a table of actors or actresses who have never won an oscar. You can use an [Anti-Join](https://learn.microsoft.com/en-us/power-query/merge-queries-left-anti) to find people who don't appear in the best_actors or best_actresses table.
6. How do the average IMDB ratings compare for movies that have either an actor or actress with an Oscar win to those that do not? Hint: Create a measure to find the total number of wins for each movie. Then make a column that checks whether this total is at least 1. 