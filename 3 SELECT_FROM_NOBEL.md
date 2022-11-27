1. 

```sql
SELECT * FROM nobel
WHERE yr = 1950
```

2. 

```sql
SELECT winner FROM nobel
WHERE yr=1962 AND subject='literature'
```

3.

```sql
SELECT yr, subject FROM nobel
WHERE winner = 'Albert Einstein'
```

4.

```sql
SELECT winner FROM nobel
WHERE subject='peace' AND yr>=2000
```

5. 

```sql
SELECT * FROM nobel
WHERE subject = 'literature' AND yr >=1980 AND yr <= 1989
```

6. 

```sql
SELECT * FROM nobel
WHERE winner in ('Theodore Roosevelt', 'Thomas Woodrow Wilson', 
'Jimmy Carter', 'Barack Obama')
```

7.

```sql
SELECT winner FROM nobel
WHERE winner LIKE 'John_%'
```

8.

```sql
SELECT * FROM nobel
WHERE (subject = 'physics' AND yr = '1980') 
OR (subject = 'chemistry' AND yr = '1984')
```

9. 

```sql
SELECT * FROM nobel
WHERE yr = 1980 AND subject not in ('chemistry', 'medicine')
```

10. 

```sql
SELECT * FROM nobel
WHERE (subject = 'Medicine' AND yr < 1910) 
OR (subject = 'Literature' AND yr >= 2004) 
```

11. 

```sql
SELECT * FROM nobel
WHERE winner = 'PETER GRÜNBERG'
```

12.

```sql
SELECT * FROM nobel
WHERE winner = 'EUGENE O''NEILL'
```

13.

```sql
SELECT winner, yr, subject FROM nobel
WHERE winner LIKE 'Sir%'
ORDER BY yr DESC, winner
```

14. (https://stackoverflow.com/questions/35446816/sqlzoo-select-from-nobel-14)

```sql
SELECT winner, subject
FROM nobel
WHERE yr = 1984
ORDER BY 
  CASE WHEN subject IN ('Physics','Chemistry') THEN 1 ELSE 0 END, 
  subject, 
  winner
```
