# SQL statements #


<!-- vim-markdown-toc GFM -->

* [SQL main statements](#sql-main-statements)
	- [Create **Table** Statement](#create-table-statement)
	- [Add records to **Table**](#add-records-to-table)
	- [Select Columns](#select-columns)
	- [Select Rows](#select-rows)

<!-- vim-markdown-toc -->

## SQL main statements ##

### Create **Table** Statement ###

```SQL
CREATE TABLE People(id INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY,
										name VARCHAR(255),
										smt VARCHAR(255)
										);
```


### Add records to **Table** ###

```SQL
INSERT INTO People	(name, smt)
										VALUES
										('Your Name', 'best');
```


### Select Columns ###

Print out all columns and rows from table **People**:
```SQL
SELECT * FROM People;
```

Print out only `name` and `smt` columns from table **People**:
```SQL
SELECT name, smt FROM People;
```


### Select Rows ###
You can specify which *rows* you want returned by using a `WHERE` filter.

```SQL
SELECT name, id FROM People WHERE id % 2 = 0;
```

This will only return rows where the column value of id is even.
