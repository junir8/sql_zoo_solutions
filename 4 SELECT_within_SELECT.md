1. 

```sql
SELECT name FROM world
WHERE population > (
    SELECT population FROM world
    WHERE name = 'Russia'
)
```

2. 

```sql
SELECT name FROM world
WHERE continent = 'Europe' AND gdp/population > (
    SELECT gdp/population FROM world
    WHERE name = 'United Kingdom'
)
```

3.

```sql
SELECT name, continent FROM world
WHERE continent in (
    SELECT continent FROM world
    WHERE name in ('Argentina','Australia')
)
```

4.

```sql
SELECT name, population FROM world
WHERE population > (
    SELECT population FROM world
    WHERE name = 'United Kingdom'
) AND population < (
    SELECT population FROM world
    WHERE name = 'Germany'
)
```

5. (https://stackoverflow.com/questions/30934951/sqlzoo-select-within-select-tutorial-5)

```sql
SELECT name, CONCAT(CAST(100*ROUND((population / (SELECT population FROM world WHERE name ='Germany')), 2) AS INT), '%')
FROM world
WHERE continent = 'Europe';
```

Note: Use CAST, otherwise, 3.0000000

6. 

```sql
SELECT name FROM world
WHERE gdp > (
    SELECT MAX(gdp) FROM world
    WHERE continent = 'Europe'
)
```

7. 

