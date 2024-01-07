# 프로그래머스 뒤에서 5등까지
#프로그래머스  
[코딩테스트 연습 - 뒤에서 5등까지 | 프로그래머스 스쿨](https://school.programmers.co.kr/learn/courses/30/lessons/181853)

## 정답
```java

import java.util.Arrays;

class Solution {
    public int[] solution(int[] num_list) {
        int[] answer = new int[5];
        //num_list에서 가장 작은 5개의 수를 오름차순으로 담은 리스트를 return
        
        Arrays.sort(num_list);
        
        for(int i=0; i<5; i++){
            answer[i] = num_list[i];    
        }
        
        return answer;
    }
}

```