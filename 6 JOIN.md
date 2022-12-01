1.

```sql
SELECT matchid, player FROM goal
WHERE teamid = 'GER'
```

2.

```sql
SELECT id,stadium,team1,team2 FROM game
WHERE id = 1012
```

3.

```sql
SELECT player, teamid, stadium, mdate 
FROM game JOIN goal ON (id = matchid)
WHERE teamid = 'GER'
```

4.

```sql
SELECT team1, team2, player
FROM game JOIN goal ON (id = matchid)
WHERE player LIKE 'Mario%'
```

5.

```sql
SELECT player, teamid, coach, gtime
FROM goal JOIN eteam ON teamid = id
WHERE gtime<=10
```

6.

```sql
SELECT mdate, teamname
FROM game JOIN eteam ON game.team1 = eteam.id
WHERE coach = 'Fernando Santos'
```

7.

```sql
SELECT player FROM game JOIN goal
ON goal.matchid = game.id
WHERE stadium = 'National Stadium, Warsaw'
```

8.

```sql

```


