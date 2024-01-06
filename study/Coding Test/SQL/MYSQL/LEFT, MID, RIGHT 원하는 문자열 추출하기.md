# LEFT
- 왼쪽에서부터 문자열 자르기
```sql
SELECT LEFT(컬럼, 가져올 개수) FROM 테이블;
```

## 프로그래머스 카테고리 별 상품 개수 구하기
#프로그래머스  
[코딩테스트 연습 - 카테고리 별 상품 개수 구하기 | 프로그래머스 스쿨](https://school.programmers.co.kr/learn/courses/30/lessons/131529)

```sql
-- 코드를 입력하세요
SELECT
    LEFT(PRODUCT_CODE, 2) AS CATEGORY,
    COUNT(*) AS PRODUCTS
FROM PRODUCT
GROUP BY CATEGORY
ORDER BY CATEGORY ASC;
```

![](https://i.imgur.com/Jx1MPzn.png)


# MID, SUBSTR, SUBSTRING
- 가운데서 특정 구간 자르기

>SUBSTR, SUBSTRING도 존재하는데 MID와 같은 기능이라고 생각하면 된다.

```sql
SELECT MID(컬럼, 시작 index, 가져올 개수) FROM 테이블;

SELECT SUBSTR(컬럼, 시작 index, 가져올 개수) FROM 테이블;

SELECT SUBSTRING(컬럼, 시작 index, 가져올 개수) FROM 테이블;
```



# RIGHT
- 오른쪽부터 문자열 자르기
```sql
SELECT RIGHT(컬럼, 가져올 개수) FROM 테이블;
```
