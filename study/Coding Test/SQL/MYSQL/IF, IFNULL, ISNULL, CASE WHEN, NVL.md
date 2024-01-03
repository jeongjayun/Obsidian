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
