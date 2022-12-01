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
SELECT DISTINCT player
  FROM game JOIN goal ON matchid = id 
    WHERE (team1='GER' OR team2='GER') AND teamid != 'GER'
```


9.

```sql
SELECT teamname, count(1) 
FROM goal JOIN eteam
ON goal.teamid = eteam.id
GROUP BY teamname
```


10.

```sql
SELECT stadium, count(1) 
FROM goal JOIN game
ON goal.matchid = game.id
GROUP BY stadium
```

11.

```sql
SELECT matchid, mdate, count(1)
FROM goal JOIN game
ON goal.matchid = game.id
WHERE team1 = 'POL' OR team2 = 'POL'
GROUP BY matchid, mdate
```

12.

```sql
SELECT matchid, mdate, count(1)
FROM game JOIN goal
ON game.id = goal.matchid
WHERE teamid = 'GER'
GROUP BY matchid, mdate
```

13.

```sql
SELECT game.mdate, team1, 
SUM(CASE WHEN goal.teamid = game.team1 THEN 1 ELSE 0 END) score1,
team2,
SUM(CASE WHEN goal.teamid = game.team2 THEN 1 ELSE 0 END) score2
FROM game LEFT JOIN goal ON matchid = id
GROUP BY mdate, team1, team2
```
