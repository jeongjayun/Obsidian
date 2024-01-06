[[GROUP BY]]
## MYSQL에서 자주 사용되는 그룹 함수들(NULL 집계 ❌)
- COUNT( ) : 그룹의 레코드 수를 반환
	- COUNT(*) : 모든 레코드 수 반환
	- COUNT(column) : 특정 컬럼 값이 NULL이 아닌 레코드 수를 반환
- SUM( ) : 그룹의 특정 컬럼 값을 합산한 결과를 반환
- AVG( ) : 그룹의 특정 컬럼 값을 평균값으로 계산한 결과를 반환
- MAX( ) : 그룹의 특정 컬럼 값 중 최대값을 반환
- MIN( ) : 그룹의 특정 컬럼 값 중 최소값을 반환

# 프로그래머스 가장 비싼 상품 구하기
#프로그래머스  
[코딩테스트 연습 - 가장 비싼 상품 구하기 | 프로그래머스 스쿨](https://school.programmers.co.kr/learn/courses/30/lessons/131697)

```sql
-- 코드를 입력하세요
SELECT
    MAX(PRICE) AS MAX_PRICE
FROM PRODUCT;
```

![](https://i.imgur.com/BeT20T7.png)