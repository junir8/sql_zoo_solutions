1. 
```sql
SELECT id, title
FROM movie
WHERE yr = 1962
```

2.
```sql
SELECT yr
FROM movie
WHERE title = 'Citizen Kane'
```

3.
```sql
SELECT id, title, yr
FROM movie
WHERE title LIKE 'Star Trek%'
ORDER BY yr
```

4.
```sql
SELECT id
FROM actor
WHERE name = 'Glenn Close'
```

5.
```sql
SELECT id
FROM movie
WHERE title = 'Casablanca'
```

6.
```sql
SELECT name FROM casting JOIN actor
ON casting.actorid = actor.id
WHERE movieid = 27
```

7.
```sql
SELECT name FROM casting JOIN actor
ON casting.actorid = actor.id
WHERE movieid = (
   SELECT id FROM movie
   WHERE title = 'Alien'
)
```

8.
```sql
SELECT DISTINCT title 
FROM movie, actor, casting
WHERE movie.id = casting.movieid AND
actor.id = casting.actorid AND actor.name = 'Harrison Ford'
```

9.
```sql
SELECT DISTINCT title 
FROM movie, actor, casting
WHERE movie.id = casting.movieid AND
actor.id = casting.actorid AND actor.name = 'Harrison Ford' AND ord <> 1
```

10.
```sql
SELECT title, actor.name
FROM movie, actor, casting
WHERE movie.id = casting.movieid AND
actor.id = casting.actorid AND yr = 1962 AND ord = 1
```

11.
```sql
SELECT yr, count(1)
FROM movie, actor, casting
WHERE movie.id = casting.movieid AND
actor.id = casting.actorid AND actor.name = 'Rock Hudson'
GROUP BY yr
HAVING count(1) > 2
```

12.
```sql
SELECT title, name FROM
(SELECT title, casting.movieid as id
FROM movie, actor, casting
WHERE movie.id = casting.movieid AND
actor.id = casting.actorid AND actor.name = 'Julie Andrews') as newmovie, actor, casting
WHERE newmovie.id = casting.movieid AND
actor.id = casting.actorid AND ord = 1
```

13.
```sql
SELECT actor.name
FROM movie, actor, casting
WHERE movie.id = casting.movieid AND
actor.id = casting.actorid
GROUP BY casting.actorid, actor.name, ord
HAVING ord = 1 AND count(1) >= 15
ORDER BY actor.name
```

14.
```sql
SELECT title, count(1)
FROM movie, actor, casting
WHERE movie.id = casting.movieid AND
actor.id = casting.actorid AND yr = 1978
GROUP BY casting.movieid, title
ORDER BY count(1) DESC, title
```

15.
```sql
SELECT DISTINCT actor.name
FROM movie, actor, casting
WHERE movie.id = casting.movieid AND
actor.id = casting.actorid AND casting.movieid in (
SELECT movieid
FROM actor JOIN casting 
ON casting.actorid = actor.id
WHERE actor.name = 'Art Garfunkel') AND actor.name <> 'Art Garfunkel'
```
