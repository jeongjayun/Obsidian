# LEFT
- 왼쪽에서부터 문자열 자르기
```sql
SELECT LEFT(컬럼, 가져올 개수)
FROM 테이블;
```

# MID
- 가운데서 특정 구간 자르기

>SUBSTR, SUBSTRING도 존재하는데 MID와 같은 기능이라고 생각하면 된다.

```sql
SELECT MID(컬럼, 시작 index, 가져올 개수) FROM 테이블;


```



# RIGHT
- 오른쪽부터 문자열 자르기
