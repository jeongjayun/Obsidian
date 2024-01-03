# IF
`IF(조건문, 참일 때의 값, 거짓일 떄의 값)`
```sql
SELECT IF ( 2 > 1 , 'TRUE' , 'FALSE' ) AS result
```

기본 사용 방식은 엑셀의 `=IF()` 와 같다. <br>
아래처럼 특정 컬럼 값의 조건에 따라 다른 컬럼의 출력하는 분기 처리도 가능하다.

```sql
SELECT IF ( column_name is null, column_1, conlumnj_2 ) AS result
```


# IFNULL
`IFNULL(column_name, value)`
```sql
SELECT IFNULL (column_name, '대체할 값' ) FROM table_name;
```

IFNULL() 함수는 해당 필드의 값이 NULL을 반환할 때, 지정한 값으로 대체하여 출력한다.<br>
아래처럼 중첩해서 사용 할 수도 있다.

```sql
SELECT IFNULL(column_name, IFNULL(column_name, '대체할 값')) FROM table_name;
```


# 프로그래머스 12세 이하 여자환자 목록 출력하기
#프로그래머스  
[코딩테스트 연습 - 12세 이하인 여자 환자 목록 출력하기 | 프로그래머스 스쿨](https://school.programmers.co.kr/learn/courses/30/lessons/132201)

```sql
-- 코드를 입력하세요
SELECT
    PT_NAME,
    PT_NO,
    GEND_CD,
    AGE,
    IFNULL(TLNO,'NONE') AS TLNO
FROM PATIENT
WHERE AGE <= 12 AND GEND_CD = 'W'
ORDER BY AGE DESC, PT_NAME ASC;

```

![](https://i.imgur.com/LDHPyJH.png)

# ISNULL
`ISNULL(column_name, value)`
```sql
SELECT ISNULL(is_discount, 0) AS result;
```
is_discount 컬럼의 값이 NULL 이라면 0, 아니라면 is_discout의 값을 출력한다.

# CASE WHEN
```sql
SELECT
	CASE
		WHEN permission_type_id = 1
		THEN '관리자'
		WHEN permission_type_id = 2
		THEN '판매자'
		ELSE '일반사용자'
	END
```
- WHEN , THEN 은 쌍을 이루어 사용해야 한다.
- WHEN (조건 혹은 값) THEN ~~ 은 여러번 사용할 수 있으며 마지막 ELSE는 모든 조건이 아닐 때 출력되는 값을 지정한다.

# NVL
```sql
SELECT
	NVL(user_name, 'no name') from users
```
user_name 컬럼 값이 null 이면 no name 을 출력하고, NULL이 아니라면 user_name 컬럼 값을 출력한다.