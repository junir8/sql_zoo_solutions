Here's the link: https://sqlzoo.net/wiki/The_nobel_table_can_be_used_to_practice_more_SUM_and_COUNT_functions.

I've finished the SUM_and_COUNT for world table. But saddly, my computer didn't save it. Thus, I do this instead.

1.

```sql
SELECT count(1) FROM nobel
```

2.

```sql
SELECT DISTINCT subject FROM nobel
```


3.

```sql
SELECT count(1) FROM nobel
WHERE subject = 'Physics'
```

4.

```sql
SELECT subject, count(1) FROM nobel
GROUP BY subject
```


5.

```sql
SELECT subject,min(yr) FROM nobel
GROUP BY subject
```

6.

```sql
SELECT subject, count(1) FROM nobel
WHERE yr = 2000
GROUP BY subject
```

7.

```sql
SELECT subject, count(DISTINCT(winner)) FROM nobel
GROUP BY subject
```

8.

```sql
SELECT subject, count(DISTINCT(yr)) FROM nobel
GROUP BY subject
```
