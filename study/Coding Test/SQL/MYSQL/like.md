# LIKE
1. SELECT문 WHERE(조건)절에서 주로 사용된다.
2. 부분적으로 일치하는 컬럼을 조회할 때 사용된다.

```SQL
SELECT * FROM 테이블명 WHERE 컬럼명 LIKE ~~~
```

- [ - ] : 글자수를 정해준다.
- '%' : 글자수를 정하지 않는다.

```SQL
--A로 시작하는 문자를 찾기--
SELECT 컬럼명 FROM 테이블 WHERE 컬럼명 LIKE 'A%'

--A로 끝나는 문자 찾기--
SELECT 컬럼명 FROM 테이블 WHERE 컬럼명 LIKE '%A'

--A를 포함하는 문자 찾기--
SELECT 컬럼명 FROM 테이블 WHERE 컬럼명 LIKE '%A%'

--A로 시작하는 두글자 문자 찾기--
SELECT 컬럼명 FROM 테이블 WHERE 컬럼명 LIKE 'A_'

--첫번째 문자가 'A''가 아닌 모든 문자열 찾기--
SELECT 컬럼명 FROM 테이블 WHERE 컬럼명 LIKE'[^A]'

--첫번째 문자가 'A'또는'B'또는'C'인 문자열 찾기--
SELECT 컬럼명 FROM 테이블 WHERE 컬럼명 LIKE '[ABC]'
SELECT 컬럼명 FROM 테이블 WHERE 컬럼명 LIKE '[A-C]'
```

## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/151137
```sql
-- 코드를 입력하세요
SELECT CAR_TYPE, COUNT(CAR_ID) AS CARS
FROM CAR_RENTAL_COMPANY_CAR
WHERE OPTIONS LIKE '%시트%'
GROUP BY CAR_TYPE
ORDER BY CAR_TYPE ASC;
```
