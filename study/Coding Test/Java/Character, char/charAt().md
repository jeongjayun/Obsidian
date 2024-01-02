# charAt()
> String으로 저장된 문자열 중에서 한 글자만 선택해서 char 타입으로 변환하는 메서드.

## 프로그래머스
#프로그래머스 
https://school.programmers.co.kr/learn/courses/30/lessons/181849

```java
class Solution {
	public int solution(String num_str) {
		int answer = 0;
		
		for(int i=0; i<num_str.length(); i++){
			 answer += num_str.charAt(i)-'0';
			  }
		return answer; }
	}
// num_str.charAt(i)-’0’ = 진짜 정수로 변환 가능 / 아니면 아스키코드 문자숫자 나옴;
```
[[Int 형변환]]

# 백준 11654 아스키코드
#백준 
[11654번: 아스키 코드](https://www.acmicpc.net/problem/11654)

## 정답
```java
package baekjoon;  
  
import java.util.Scanner;  
  
public class No11654 {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  
        String str= scanner.nextLine();  
        int intValue = str.charAt(0);  // 아스키 코드로 문자 변환
        System.out.println(intValue);  
    }  
}
```

[[../../Code up 기초100제/1031 ~ 1045|1031 ~ 1045]] 중에 1037번도 같은 문제.