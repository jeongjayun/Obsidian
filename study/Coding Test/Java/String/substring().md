#String 
# substring()
>문자열을 자를 때 사용하는 메서드

https://hianna.tistory.com/534

```java
//how to use
public String substring(int startIndex) // 처음부터 끝까지
public String substring(int startIndex, endIndex) // 범위 지정
```

## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/181907

```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = my_string.substring(0,n);
        return answer;
    }
}
```