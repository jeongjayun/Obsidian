# Double -> String
## Double.toString()

```java
Double doubleFormat = 777.77;
String changeFormat = Double.toString(doubleFormat);
```

# Double -> Int
## (int)Math.round(doubleFormat);

```java
Double doubleFormat = 777.77;
int changeFormat = (int)Math.round(doubleFormat);

// Math 클래스의 round 메서드에 변수를 넣은 다음 형변환 값을 받습니다.
// 이때 받는 값은 반올림이 되어 받아지게 됩니다.
```

## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/181850

```java
class Solution {
    public int solution(double flo) {
        int answer = 0;
        
        answer = (int)Math.round(flo);
        
        return answer;
    }
}

//근데 테스트케이스에서 오류남

class Solution {
    public int solution(double flo) {
        int answer = 0;
        
        answer = (int)Math.floor(flo);
        
        return answer;
    }
}

//소수점 아래 버림해야 정답임
```

[[Math.round()]],[[Math.floor()]]
# Double -> Long
## (new Double(doubleFormat)).longValue();

```java
Double doubleFormat = 777.77;
Long  changeFormat = (new Double(doubleFormat)).longValue();

//Double 타입의 변수에 longValue() 메서드를 사용하는 방법이 있습니다.
```