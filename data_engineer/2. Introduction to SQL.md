# Introduction to SQL

```
CREATE VIEW employee_hire_years AS 
SELECT id, name, year_hired 
FROM employees;
```

- We create a view called `employee_hired_years` by assigning the results of a query selecting three fields from the employees table to a new view.
- There is **no result set** when creating a view

## `SELECT * FROM employee_hire_years;`
- Once a view is created, however, we can query it just as we would a normal table by selecting FROM the view.


## alias(AS)를 쓰는 이유
- SQL 결과 set만 보고도 쿼리의 의도를 파악할 수 있고 쉽게 이해할 수 있다.
- 심지어, SQL을 모르는 사람에게도 이해가능한 결과를 보여줄 수 있다.

## CREATE VIEW 를 쓰는 이유
- 우리가 원하는 정보를 데이터베이스의 직접적인 수정 없이 빠르게 접근하기 위해 테이블을 만드는 용도이다.

## PostgreSQL 
- Research funds provided by DARPA
- FREE and OPEN SOURCE
- Developed at the University of California,Berkeley
- LIMIT keyword

## SQL server
- Created by Microsoft
- Queried using T-SQL
- Has both free and enterprise versions
- SELECT TOP() keyword 
