# 현재 날짜와 시간
```sql
SELECT SYSDATE(), NOW() FROM DUAL
```

# 현재 날짜
```sql
SELECT CURDATE(), CURRENT_DATE() FROM DUAL
```

# 현재 시간
```sql
SELECT CURTIME(), CURRENT_TIME() FROM DUAL
```

# 현재 년, 월, 일
```sql
SELECT
YEAR(NOW()), MONTH(NOW()), DAYOFMONTH(NOW())
FROM DUAL
```

# 요일
```sql
SELECT
DAYOFWEEK(NOW()), WEEKDAY(NOW())
FROM DUAL

/*DAYOFWEEK 데이터 값 : 1-일요일, 2-월요일, 3-화요일, 4-수요일, 5-목요일, 6-금요일, 7-토요일*/
/*WEEKDAY 데이터 값 : 0-월요일, 1-화요일, 2-수요일, 3-목요일, 4-금요일, 5-토요일, 6-일요일*/
```

# 1년 중 며칠이 지났는지 확인
```sql
SELECT DAYOFYEAR(NOW())
FROM DUAL
```