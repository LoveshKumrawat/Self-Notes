# **Postgres Important DB Commands**
<br>

> **Copies the schema, data but not constraints to new table**

	SELECT * INTO <newTable> FROM <table>;
---
> **Bug: Copies the data without any column to new table**

	SELECT INTO <newTable> FROM <table>;
---
> **Copies the data to another table having same schema**

	INSERT INTO <table> SELECT * FROM <table> WHERE <condition>;
---
> **Empty given table**

	TRUNCATE TABLE <table>;
---
> **Empty given table with refrenced table**

	TRUNCATE TABLE <table> CASCADE; 
---
> **Empty given table with refrenced table & reset SERIAL**

	TRUNCATE TABLE <table> RESTART IDENTITY CASCADE;
---
> **Display the User Privileges**

	SELECT * FROM information_schema.table_privileges;
---
> **Display the values of Enum**

	SELECT enum_range(NULL::<typeName>);
---