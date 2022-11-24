# Mainframes Common SQL/DB2 CODES and resolution

By [admin](http://www.techtricky.com/author/admin/) [DB2](http://www.techtricky.com/category/mainframes/database/) [0 Comments](http://www.techtricky.com/mainframes-common-sql-db2-codes-and-resolution/#respond)

**Mainframes Common SQL/DB2 CODES and resolution**

180 to 189 date related

- 180 –> Invalid date format.
- 203 –> reference column is ambiguous.. IT NEEDS TO BE QUALIFIED AS IT EXISTS IN MULTIPLE TABLES.
  This Comes when same column name exists in multiple tables (or same table is being used multiple times in same SQL) which are part of the SQL statement and proper qualification is not given.
- 204 –> Undefined table name. This comes when the table name given is misspelled or does not exist.
- 205 –> Column is not a column of table mentioned.
- 208 –> Order by Clause is invalid as column name is not part of result table.
- 216 –> THE NUMBER OF ELEMENTS ON EACH SIDE OF A PREDICATE OPERATOR DOES NOT MATCH. PREDICATE OPERATOR IS operator.
- 305 –> Null value error. If null indicator is not specified and data has a null value then this SQL code would be returned.
- 311 –> Error while inserting or updating a VARCHAR column. This occurs when the receiving field length is not set correctly.
- 313 –> Number of host variables and number of columns returned.
- 354 –> It occurs for ROWSET cursors. When ROWSET FETCH returns more than 1 row but if there are non terminating errors then it throws -354 sqlcode. Can be resolved by using the GET DIAGNOSTICS to get the error details.
- 402 –> Arithmetic operations performed on a Character date-time data.
- 407 –> When trying to update or insert a NUll value into a Column which is defined as NOT NULL.
- 500 –> Cursor closed with the connection lost.
- 501 –> cursor used in Fetch or Close is not in Open state. In this case, Cursor might have opened before to Fetch or Close but it could have been closed in between. May be because of any commits in between or something else.
- 502 –> Trying open an already opened cursor. If the cursor is being opened and Closed multiple times, check whether it is being closed in each loop.
- 503 –> Update cursor issue. Columns which are to be updated should be specified in the cursor declaration. Only the specified columns should be updated. Otherwise it throws -503.
- 504 –> Cursor referenced is not declared. Check the cursor name declared to see both declared and referenced or same. If the name is different change it while referencing. Otherwise declare it.
- 507 –> It occurs in Update or Delete cursor when the cursor name referenced is not OPENed.
- 514 –> Throws this for dynamic SQLs when the cursor is not prepared when referencing.
- 531 –> Referential integrity related. When updating a Parent Key in parent table which has one or more dependent rows in Child tables.
- 532 –> If the delete constraint is defined and trying to delete that row it throws this error.
- 543 –> When Check constraint is in effect and trying to delete the row from parent table.
- 603 –> Occurs while creating a Unique Index when the table contains Duplicates for the identified columns.
- 719 –> Package already exists while performing the BIND Add.
- 702 –> Package version already exists while performing the BIND REPLACE with Version.
- 723 –> Throws this when the Table has Triggers defined on them and there is an error while executing that trigger. For example if a Trigger defined on table such that for every row Updated, the previous value should be inserted into a History Table. So when we update the base table with a new value, Trigger gets activated and inserts a row in to the History Table. But the row with same key already exists in the History table, then the trigger fails with -723.
- 803 –> Occurs when trying to insert a Duplicate row.
- 805 –> Plan not found error. It happens while running a COBOL-DB2 program and the plan specified is not found. Check the whether plan name given.
- 811 –> It occurs for Singleton SQL statements used in a application program. Singleton SQL statement can handle only one result as it has Only one set of host variables to handle the data. But if more than one row is returned, db2 throws -811. This can be handled by evaluating the SQLCODE by specifying if SQLCODE =-811 CONTINUE so that only one row gets selected. Otherwise use of CURSORS will solve the multiple rows issue.
- 818 –> Time stamp mismatch between Load module and Bind output. Check whether the correct load modules are used. It can occur if we are have compiled and Link edited the source code in to Test Load Library but used Prod Load Libraries while running the job.
- 904 –> when the resource referenced is not available. Try after waiting for some time can resolve this issue in some cases.
- 911 –> Current unit of work has been rolled back because of a Dead lock and Time Out.
- 918 –> Connection Lost
- 922 –> Authorization error.



### For Further Reading==>



- [Handling Null Values in COBOL DB2](http://www.techtricky.com/handling-null-values-in-cobol-db2/)
- [DB2 Group By and Order By Clauses](http://www.techtricky.com/db2-group-by-and-order-by-clauses/)
- [Scrollable Cursors In DB2 Mainframes](http://www.techtricky.com/scrollable-cursors-in-db2-mainframes/)
- [Index Optimization Tips in DB2](http://www.techtricky.com/index-optimization-tips-in-db2/)
- [CTS Mainframe Interview Questions](http://www.techtricky.com/cts-mainframe-interview-questions/)