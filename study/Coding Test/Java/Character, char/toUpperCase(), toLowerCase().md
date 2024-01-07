>[!note] 틀린 이유
>[[Character.isLowerCase()]] 랑 헷갈렸다.
>- isLowerCase 는 소문자인지 대문자인지 확인 후 True, False 반환
>- toUpperCase, toLowerCase 소문자인지 대문자인지 확인 후 대문자로 / 소문자로 변환

# 프로그래머스 배열에서 문자열 대소문자 변환하기
#프로그래머스  
[코딩테스트 연습 - 배열에서 문자열 대소문자 변환하기 | 프로그래머스 스쿨](https://school.programmers.co.kr/learn/courses/30/lessons/181875)

## 정답
```java

class Solution {
    public String[] solution(String[] strArr) {
        String[] answer = new String[strArr.length];
        
        for(int i=0; i < strArr.length ;i++){
            if(i % 2 == 0){
                answer[i] = strArr[i].toLowerCase();
            } else {
                answer[i] = strArr[i].toUpperCase();
            }
        }
        
        return answer;
    }
}

```
![](https://i.imgur.com/e0X26Cj.png)
