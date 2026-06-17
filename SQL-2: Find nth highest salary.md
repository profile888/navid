# These SQL queries finds the nth highest salary:


### -- 1. DISTINCT, ORDER BY, and OFFSET/FETCH (single SELECT statement)
```
select distinct sal
  from emp
  WHERE sal IS NOT null
  order by sal desc
  offset 3 rows fetch next 1 row only;
```


### -- 2. Salary using GROUP BY and OFFSET/FETCH (single SELECT statement)
```
select sal
  from emp
  WHERE sal IS NOT null
  group by sal
  order by sal desc
  offset 3 rows fetch next 1 row only;
```


### -- 3. Find second highest salary using DISTINCT, ORDER BY, and OFFSET/FETCH
```
SELECT sal AS second_highest_sal
FROM (
    SELECT DISTINCT sal
    FROM emp
    WHERE sal IS NOT null
    ORDER BY sal DESC
)
OFFSET 4 ROW FETCH NEXT 1 ROW ONLY;
```


### -- 4. Using subquery with FETCH FIRST (LIMIT equivalent)
```
SELECT MIN(sal)
FROM (
    SELECT DISTINCT sal
    FROM emp
    WHERE sal IS NOT NULL
    ORDER BY sal DESC
    FETCH FIRST 4 ROWS ONLY
);
```


### -- 5. Using MIN and ROWNUM with subquery
```
SELECT MIN(sal) AS third_highest
FROM (
    SELECT DISTINCT sal
    FROM emp
    WHERE sal IS NOT null
    ORDER BY sal DESC
)
WHERE ROWNUM <= 4;
```


### -- 6. Using WITH clause (CTE) with DENSE_RANK
```
WITH ranked_salaries AS (
    SELECT DISTINCT sal,
           DENSE_RANK() OVER (ORDER BY sal DESC) AS drnk
    FROM emp
)
SELECT sal
FROM ranked_salaries
WHERE drnk = 4;
```


### -- 7. Using WITH clause (CTE) as a temporary result set
```
SELECT sal
from
(WITH tempp AS (SELECT sal
				FROM emp
				WHERE sal IS NOT NULL
				GROUP BY sal
				ORDER BY sal desc
				)
SELECT sal, rownum AS rn
  FROM tempp)
WHERE rn = 4;
```


### -- 8. Using nested subqueries with MAX function
```
SELECT MAX(sal)
FROM emp
WHERE sal < (
    SELECT MAX(sal)
    FROM emp
    WHERE sal < (
        SELECT MAX(sal)
        FROM emp
    )
);
```


### -- 9. Using self-join logic with COUNT(DISTINCT) and ROWNUM
```
SELECT e1.sal
FROM emp e1
WHERE 4 = (
    SELECT COUNT(DISTINCT e2.sal)
    FROM emp e2
    WHERE e1.sal < e2.sal
)
AND ROWNUM = 1;
```


### -- 10. Using DENSE_RANK (modern approach)
```
SELECT DISTINCT sal
FROM emp
QUALIFY DENSE_RANK() OVER (ORDER BY sal DESC) = 4;
```


### -- 11. Using Common Table Expression (CTE) with ranking
```
WITH ranked_salaries AS (
    SELECT DISTINCT sal,
           DENSE_RANK() OVER (ORDER BY sal DESC) AS rnk
    FROM emp
)
SELECT sal
FROM ranked_salaries
WHERE rnk = 4;
```


### -- 12. Traditional ROWNUM approach
```
SELECT sal
FROM (
    SELECT DISTINCT sal
    FROM emp
    ORDER BY sal DESC
)
WHERE ROWNUM <= 5;
```


### -- 13. MINUS with ROWNUM approach
```
SELECT MIN(SAL)
  FROM
(SELECT SAL FROM EMP
MINUS
SELECT MIN(SAL) FROM EMP
ORDER BY SAL DESC)
WHERE ROWNUM <=5;
```


### -- 14. Using DENSE_RANK (modern window function approach)
```
SELECT DISTINCT sal
FROM (
    SELECT sal, DENSE_RANK() OVER (ORDER BY sal DESC) AS rnk
    FROM emp
)
WHERE rnk = 4;
```


### -- 15. Using ROWNUM with nested query ordering
```
SELECT sal FROM (
    SELECT sal, ROWNUM AS rn FROM (
        SELECT DISTINCT sal 
        FROM emp 
        ORDER BY sal DESC
    )
) WHERE rn = 4;
```
