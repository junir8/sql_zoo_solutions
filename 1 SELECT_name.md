12.

```sql
SELECT name FROM world
WHERE capital = concat(name, ' City')
```

13.

```sql
SELECT capital, name FROM world
WHERE capital LIKE concat('%', name, '%')
```

14.

```sql
SELECT capital, name FROM world
WHERE capital LIKE concat(name, '_%')
```

15.

```sql
SELECT name, REPLACE(capital, name, '') as extension FROM world
WHERE capital LIKE concat(name, '_%')
```
