# 그룹 함수
- 여러 개의 레코드를 하나의 그룹으로 묶어서 계산을 수행한다.

## MYSQL에서 자주 사용되는 그룹 함수들(NULL 집계 ❌)
- COUNT( ) : 그룹의 레코드 수를 반환
	- COUNT(*) : 모든 레코드 수 반환
	- COUNT(column) : 특정 컬럼 값이 NULL이 아닌 레코드 수를 반환
- SUM( ) : 그룹의 특정 컬럼 값을 합산한 결과를 반환
- AVG( ) : 그룹의 특정 컬럼 값을 평균값으로 계산한 결과를 반환
- MAX( ) : 그룹의 특정 컬럼 값 중 최대값을 반환
- MIN( ) : 그룹의 특정 컬럼 값 중 최소값을 반환

# 프로그래머스 성분으로 구분한 아이스크림 총 주문량
#프로그래머스  
[코딩테스트 연습 - 성분으로 구분한 아이스크림 총 주문량 | 프로그래머스 스쿨](https://school.programmers.co.kr/learn/courses/30/lessons/133026)

```sql
-- 코드를 입력하세요
SELECT INGREDIENT_TYPE, SUM(TOTAL_ORDER) AS TOTAL_ORDER
FROM FIRST_HALF AS f LEFT JOIN ICECREAM_INFO AS i ON f.FLAVOR=i.FLAVOR
GROUP BY INGREDIENT_TYPE;
```

![](https://i.imgur.com/IGkH1jq.png)

# 사용법
## 컬럼 그룹화
```sql
SELECT 컬럼 FROM 테이블 GROUP BY 그룹화할 컬럼;
```

## 조건 처리 후에 컬럼 그룹화
```sql
SELECT 컬럼 FROM 테이블 WHERE 조건식 GROUP BY 그룹화할 컬럼;
```

## 컬럼 그룹화 후에 조건 처리
```sql
SELECT 컬럼 FROM 테이블 GROUP BY 그룹화할 컬럼 HAVING 조건식;
```

## 조건 처리 후에 컬럼 그룹화 후에 조건 처리
```sql
SELECT 컬럼 FROM 테이블 WHERE 조건식 GROUP BY 그룹화할 컬럼 HAVING 조건식;
```

## ORDER BY가 존재하는 경우
```sql
SELECT 컬럼 FROM 테이블 [WHERE 조건식]
GROUP BY 그룹화할 컬럼 [HAVING 조건식] ORDER BY 컬럼1 [, 컬럼2, 컬럼3 ...];
```


