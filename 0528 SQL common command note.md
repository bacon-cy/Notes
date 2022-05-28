---
title: 0528 SQL note
---
>reference : https://developer.android.com/codelabs/basic-android-kotlin-training-sql-basics?continue=https%3A%2F%2Fdeveloper.android.com%2Fcourses%2Fpathways%2Fandroid-basics-kotlin-unit-5-pathway-1%23codelab-https%3A%2F%2Fdeveloper.android.com%2Fcodelabs%2Fbasic-android-kotlin-training-sql-basics#0

### common SQL statements
`SELECT`
Gets specific information from a data table and results can be filtered and sorted in various ways.

`INSERT`
Adds a new row to a table.

`UPDATE`
Updates an existing row (or rows) in a table.

`DELETE`
Removes an existing row (or rows) from a table.
## SELECT
### common SQL clause
`FROM`
 the `FROM` keyword followed by the name of the data table

`WHERE`
 lets you filter results based on one or more columns.
 >Note : 
 >in SQL, you only use a single equal sign to compare two values.

`LIMIT`
 set a limit on the number of rows returned

 `DISTINCT`
 only gets different values set
 > SELECT COUNT(DISTINCT _type) FROM _tableName

`ORDER BY`
>SELECT _columnName FROM _tableName ORDER BY _columnName DESC

By default, results are sorted in ascending order, but you can add either the `ASC` or `DESC` keyword to the order by clause to sort in ascending or descending order. 

`GROUP BY`
>SELECT _columnName FROM _tableName GROUP BY _columnname2 ORDER BY _columnName3

>This is best understood using an example. Instead of counting all the parks in the database, you can see how many parks of each type are present, and get a separate count for each.
>SELECT type, COUNT(*) FROM park GROUP BY type ORDER BY type

`AND` `OR`
Boolean Operators just like `&&` and `||`

### common SQL functions
`COUNT()`
return a count(type:int)
> SELECT COUNT(*) FROM _tableName

`SUM(column_name)`
>SELECT SUM(_amount) FROM _tableName WHERE _type = "_type3"

`MAX()` `MIN()`

## INSERT
`INSERT` statement is followed by the clause `INTO` and `VALUES`
>INSERT INTO _tableName VALUES(_column1Value, _column2Value, ...)

>Note : ID
>Also notice that you pass in null for the ID. While you can provide a specific number, this isn't exactly convenient as your app would have to keep track of the latest ID to make sure there are no duplicates. You can, however, configure your database so that the primary key is automatically incremented, which was done here. That way you can pass in null, and the next ID is chosen automatically.

## UPDATE
```
UPDATE _tableName
SET column1 = ...,
column2 = ...,
...
WHERE _columnName = _myColumnName
```
## DELETE
```
DELETE FROM _tableName
WHERE _columnName = _myColumnName

