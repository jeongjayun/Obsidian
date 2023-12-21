# Character.isLowerCase()
>주어진 문자가 소문자인지 여부를 확인하여 true 또는 false를 반환한다.


## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/181877

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        
        String answer=""; //초기화
        
        for(int i=0;i<a.length();i++){
            char c=a.charAt(i);
            if(Character.isLowerCase(c)){
                answer=answer+Character.toUpperCase(c);
            } else {
                answer=answer+Character.toLowerCase(c);
            }
        }
        
        System.out.println(answer);
    }
}
```

https://school.programmers.co.kr/learn/courses/30/lessons/181876
```java
class Solution {
    public String solution(String myString) {
        String answer = "";
        
        for(int i=0; i<myString.length(); i++){
        char c = myString.charAt(i);
            
            if(Character.isLowerCase(c)){
                answer = answer + Character.toLowerCase(c); 
            } else {
                answer = answer + Character.toLowerCase(c);
            }
            
        }
        
        return answer;
    }
}
```