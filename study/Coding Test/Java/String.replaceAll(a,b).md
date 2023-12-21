#String 
# String.replaceAll(a,b)
## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/181863

```java
class Solution {
    public String solution(String rny_string) {
        String answer = rny_string.replaceAll("m","rn"); 
        return answer;
    }
}
```

## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/181873

```java
class Solution {
    public String solution(String my_string, String alp) {
        String answer = "";
        
        return my_string.replaceAll(alp, alp.toUpperCase());
    }
}
```