# DB2 Optimizer Overview | How Db2 selects the optimum path

By [admin](http://www.techtricky.com/author/admin/) [DB2](http://www.techtricky.com/category/mainframes/database/) [0 Comments](http://www.techtricky.com/db2-optimizer-overview-how-db2-selects-the-optimum-path/#respond)

**The DB2 optimizer** is the main component of DB2. As its name implies, it analyzes the SQL statements and determines the most efficient path to access the desired data from the tables.

When the SQl statement is fired, it access the statistics stored in the DB2 catalog to determine the best path to suffice the SQL statement.

optimizer performs the following to get the best access path:

- Verifies the Syntax of the SQL
- Determines the table(s) to be accessed
- Identifies the columns from those tables to be returned
- Columns in the SQL statement’s predicates
- Idexes for this combination of tables and columns
- What statistics are available in the DB2 catalog

Based on this information, the optimizer analyzes the possible access paths and chooses the best one for the given query. An access path is the navigation logic used by DB2 to access the requisite data. A table space scan using sequential pre-fetch is an example of a DB2 access path.

Based on models developed by IBM for estimating the cost of CPU and I/O time, the impact of uniform and non-uniform data distribution, and the state of table space and indexes, the optimizer usually arrives at a good estimate of the optimal access path.

![db2 Optimizer Overview Diagram](http://www.techtricky.com/wp-content/uploads/2018/04/db2-Optimizer-Overview-Diagram.png)



### For Further Reading==>



- [DB2 Table Space Types and its usage](http://www.techtricky.com/db2-table-space-types-and-its-usage/)
- [Index Optimization Tips in DB2](http://www.techtricky.com/index-optimization-tips-in-db2/)
- [Joins and Unions in DB2](http://www.techtricky.com/joins-and-unions-in-db2/)
- [Cobol-DB2 Cursor Overview](http://www.techtricky.com/cobol-db2-cursor-overview/)