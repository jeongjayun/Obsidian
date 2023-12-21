#String #형변환

# String -> Int
## Integer.parseInt();

```java
String stringFormat = "777";
int intFormat = Integer.parseInt(stringFormat);
```

## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/181848

```java
class Solution {
    public int solution(String n_str) {
        int answer = 0;
        
        answer = Integer.parseInt(n_str);
        
        return answer;
    }
}
```
# String -> Double
## Double.parseDouble();

```java
String stringFormat = "777";
Double changeFormat = Double.parseDouble(stringFormat);
```

# String -> Long
## Long.parseLong();

```java
String stringFormat = "777";
Long changeFormat = Long.parseLong(stringFormat);
```

# String -> char
## stringFormat.charAt();

```java
String stringFormat = "123";
char changeFormat = stringFormat.charAt(0);

//string에서 char로 변경할 경우 
//자바에서 제공하는 charAt를 사용하면 됩니다.
//예를 들어, charAt의 괄호 인덱스가 0일 경우 1이 리턴되고 1일 경우 2, 2일 경우 3 이 리턴되게 됩니다.
```

