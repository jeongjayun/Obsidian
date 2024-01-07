기본적으로 **사용자가 지정한 것(문자열, 컬럼) 등의 글자를 합쳐**주거나 **일괄적으로 글자를 추가**하려고 할 때 사용한다.

```sql
CONCAT (string1, string2, string3, ...)

/* 예시 */
CONCAT("May be A-Z", "or", "may be 0-9")
/* 결과 */
May be A-Z or may be 0-9
```

# 사용 형태
1. 문자열을 연결하여 출력
	```sql
	SELECT CONCAT('test', 'is', 'first');
	/* 결과 */
	testisfirst
	```
2. 각 열끼리의 연결 및 일괄적으로 문자열 삽입

	| ID_NUM | NAME   | COUNTRY  | CITY         |
	| ------ | ------ | -------- | ------------ |
	| 1      | 강박사 | 대한민국 | 서울         |
	| 2      | 줄줄이 | 대한민국 | 부산         |
	| 3      | 정빵디 | 러시아   | 블라디보스톡 |
	| 4      | 조상팡 | 프랑스   | 파리         |
	| 5      | 이한송 | NULL     | 퀘백         |

	```sql
	SELECT CONCAT(COUNTRY, '--->', CITY)
	/* COUNTRY,CITY는 컬럼이므로 감싸지 않음 */
	/* 결과 */
	대한민국-->서울대한민국-->부산
	러시아-->블라디보스톡
	프랑스-->파리
	NULL
	```

1. WHERE 절에 사용한 CONCAT
	``` sql
	SELECT CONCAT(COUNTRY, '(', CITY, ')')
	FROM 테이블
	WHERE CONCAT(ID_NUM, '_', NAME) = "4_조상팡";
	-- ID_NAME=4_조상팡에 해당하는 조건 --
	결과 : 프랑스(파리)
	```

# 참고
1. **CONCAT**의 인수 중, **하나라도 NULL이 들어있으면 NULL로 출력**된다. 위의 표에서 이한송이라는 사람은 COUNTR에 값이 없는 NULL로 표현되어 있다. CONCAT을 활용하여 사용하여도 결과는 무조건 NULL 이 된다.
2. 이 <font color="#c0504d">함수로 반환되는 것은 문자열</font>이다.

# 조회수가 가장 많은 중고거래 게시판의 첨부파일 조회하기
#프로그래머스  
[코딩테스트 연습 - 조회수가 가장 많은 중고거래 게시판의 첨부파일 조회하기 | 프로그래머스 스쿨](https://school.programmers.co.kr/learn/courses/30/lessons/164671)

```sql
-- 코드를 입력하세요
SELECT
    CONCAT("/home/grep/src/",F.BOARD_ID,"/",F.FILE_ID,F.FILE_NAME,F.FILE_EXT)
    AS FILE_PATH
FROM
    USED_GOODS_FILE AS F
    JOIN USED_GOODS_BOARD AS B
    ON F.BOARD_ID = B.BOARD_ID
WHERE B.VIEWS = (SELECT MAX(VIEWS) FROM USED_GOODS_BOARD)
ORDER BY F.FILE_ID DESC;
```

![](https://i.imgur.com/JpLYjJq.png)
