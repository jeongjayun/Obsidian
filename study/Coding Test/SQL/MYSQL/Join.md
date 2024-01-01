![](https://i.imgur.com/AS69awH.png)

# JOIN의 종류
## INNER JOIN
- 두 테이블에서 같은 값만 출력한다.

```sql
SELECT * FROM people AS p INNER JOIN university AS u ON p.ID = u.UID;
-- INNER 생략 가능하다.
SELECT * FROM people AS p JOIN university AS u ON p.ID = u.UID;
```

**사용법**
1. INNER JOIN 좌우에 결합한 테이블 명을 작성 :  `people`**INNER** `university`
2. AS로 별명을 붙이고
3. ON 뒤에 결합 조건을 명시.

![](https://i.imgur.com/TcIe5mx.png)


## OUTER JOIN
### LEFT JOIN
- 왼쪽 테이블을 기준으로 오른쪽 테이블을 매치
- 왼쪽 테이블의 한 개의 레코드에 여러개의 오른쪽 테이블 레코드가 일치할 경우, 해당 왼쪽 레코드를 여러번 표시한다.
- 왼쪽은 무조건 표시하고, 매치되는 레코드가 없으면 NULL 표시.

### RIGHT JOIN
- 오른쪽 테이블을 기준으로 왼쪽 테이블을 매치.
- LEFT JOIN에서 방향만 오른쪽으로 바꾼 것이므로, 해당 레코드가 여러번 표시되거나 NULL표시.

## CROSS JOIN
- 조건에 부합되지 않는 행까지 포함시켜 결합하는 것 (모든 경우의 수를 포함한다.)

```sql
SELECT * FROM Meals, Drinks
SELECT * FROM Meals CROSS JOIN Drinks;
```

![](https://i.imgur.com/fmnOkeg.png)


