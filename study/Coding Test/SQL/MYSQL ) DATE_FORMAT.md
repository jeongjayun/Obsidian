[[MYSQL ) DATE 날짜와 시간 관련 함수]]

- 특정 날짜를 사용자가 원하는 형태로 변경
- MySQL에서 기본적으로 제공해주는 DATE_FORMAT() 함수에 변환할 날짜와 '-, .' 등의 구분자를 넣어서 사용.

| 포맷문자 | 설명(예시)              | 포맷문자 | 설명(예시)              |
| -------- | ----------------------- | -------- | ----------------------- |
| %Y       | 년도(2021)              | %m       | 월(01, 02, 11)          |
| %y       | 년도(21)                | %c       | 월(1, 8)                |
| %d       | 일(01, 19)              | %M       | 월(January, August)     |
| %e       | 일(1, 19)               | %b       | 월(Jan, Aug)            |
| %T       | 시간(12:30:00)          | %W       | 요일(Wednesday, friday) |
| %r       | 시간(12:30:00 AM)       | %a       | 요일(Wed, Fri)          |
| %H       | 24시간 시간(01, 14, 18) | %i       | 분(00)                  |
| %l       | 12시간 시간(01, 02, 06) | %S       | 초(00)                  |

# 프로그래머스 조건에 맞는 도서리스트  출력하기
#프로그래머스  
[코딩테스트 연습 - 조건에 맞는 도서 리스트 출력하기 | 프로그래머스 스쿨](https://school.programmers.co.kr/learn/courses/30/lessons/144853)

```sql
-- 코드를 입력하세요
SELECT  BOOK_ID,
		DATE_FORMAT(PUBLISHED_DATE, "%Y-%m-%d") AS PUBLISHED_DATE FROM BOOK
WHERE CATEGORY ='인문' AND YEAR(PUBLISHED_DATE) = 2021 
ORDER BY PUBLISHED_DATE ASC;
```

![](https://i.imgur.com/YeoExNi.png)
