# charAt()
> String으로 저장된 문자열 중에서 한 글자만 선택해서 char 타입으로 변환하는 메서드.

## 프로그래머스
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
