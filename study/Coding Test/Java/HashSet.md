# 백준 3052 나머지
#백준 
[3052번: 나머지](https://www.acmicpc.net/problem/3052)

### 내가 쓴 오답
```java
package baekjoon;  
  
import java.util.Scanner;  
  
public class No3052 {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  
  
        int[] Arr = new int[10];  
        for (int i = 0; i < 10; i++) {  
            Arr[i] = scanner.nextInt() % 42;  
        }  
  
        int cnt =1; //서로 다른 수 찾기  
        for (int i = 0; i < Arr.length-1; i++) {  
            if (Arr[i] != Arr[i + 1]) {  
                cnt++;  
            }  
        }  
        System.out.println(cnt);  
        scanner.close();  
    }  
}
```

두번째 로직에서 오류가 있었다. 현재의 로직으로는 현재 나머지가 다음 나머지와 다를 때마다 `cnt`를 증가시키고 있지만 하지만 문제에서 요구하는 것은 고유한 나머지의 개수를 세는 것입니다.

###  풀이

#### 문제 분석

```
// 슈도 코드 작성
수 10개를 입력받을 배열을 만든다.
입력된 수는 42로 나누어 나머지를 배열에 담는다.
배열에 입력된 값을 비교하여
서로 다른 값이 몇개인지 출력한다.
```

## 정답
```java

import java.util.HashSet;
import java.util.Scanner;
import java.util.Set;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // HashSet을 사용하여 중복을 허용하지 않는 집합을 만듭니다.
        Set<Integer> remainders = new HashSet<>();

        for (int i = 0; i < 10; i++) {
            int num = scanner.nextInt();
            // 입력받은 숫자를 42로 나눈 나머지를 집합에 추가합니다.
            remainders.add(num % 42);
        }

        // 집합의 크기가 서로 다른 나머지의 개수입니다.
        System.out.println(remainders.size());

        scanner.close(); // 스캐너를 닫아줍니다.
    }
}

```