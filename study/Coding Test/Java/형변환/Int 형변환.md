#Integer 

# Int -> String
## Integer.toString();

```java
int intFormat = 777;
String stringFormat = Integer.toString(intFormat);
```

## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/181845

```java
class Solution {
    public String solution(int n) {
        String answer = "";
        
        answer = Integer.toString(n);
        
        return answer;
    }
}
```
# Int -> Long
## Long.valueOf();

```java
int intFormat = 777;
Long  changeFormat = Long.valueOf(intFormat);
```
# Int -> Double
## Double.valueOf();

```java
int intFormat = 777;
Double  changeFormat = Double.valueOf(intFormat);
```

# Int -> char
## (char)(intFormat+'0');

```java
int intFormat = 1;
char changeFormat = (char)(intFormat+'0');

// 타입캐스팅을 처리하여 아스키코드값을 추출할 수 있습니다.
// 여기서 입력한 '1'에 대한 숫자를 얻으려면 
// 아스키코드값의 '0'에 해당하는 값만큼 더해주면 됩니다.
```
[[charAt()]]