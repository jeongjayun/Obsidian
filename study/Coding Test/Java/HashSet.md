# Set
>[!info] Set이란?
>인터페이스 구현 클래스<br>
>1. 객체를 **중복해서 저장할 수 없으며**, **하나의 null 값만 저장**할 수 있다.
>2. **중복을 자동으로 제거**해준다.

Set은 <u>비선형 구조</u>이기 때문에 <u>'순서' 의 개념과 '인덱스'가 존재하지 않는다</u>. 때문에 값을 추가/삭제하는 경우 Set의 내부에 해당 값을 검색하여 해당 기능을 수행해야 한다. <u>그래서 처리 속도가 List구조에 비해 느리다</u>는 단점이 있다.

# HashSet
>[!info] Hsh


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

두번째 로직에서 오류가 있었다. 현재의 로직으로는 현재 나머지가 다음 나머지와 다를 때마다 `cnt`를 증가시키고 있지만 문제에서 요구하는 것은 **고유한 나머지의 개수**를 세는 것이다.

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