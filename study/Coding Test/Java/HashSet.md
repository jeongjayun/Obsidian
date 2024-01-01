# Set
![](https://i.imgur.com/nDKi5uQ.png)

>[!info] Set이란?
>인터페이스 구현 클래스<br>
>1. 객체를 **중복해서 저장할 수 없으며**, **하나의 null 값만 저장**할 수 있다.
>2. **중복을 자동으로 제거**해준다.

Set은 <u>비선형 구조</u>이기 때문에 <u>'순서' 의 개념과 '인덱스'가 존재하지 않는다</u>. 때문에 값을 추가/삭제하는 경우 Set의 내부에 해당 값을 검색하여 해당 기능을 수행해야 한다. <u>그래서 처리 속도가 List구조에 비해 느리다</u>는 단점이 있다.

# HashSet
>[!info] HashSet 이란?
>`Set 인터페이스`에서 지원하는 구현 클래스로 `Set`의 성질을 그대로 상속받는다.

## HashSet의 성질
1. 중복된 값을 허용하지 않는다.
	- **값의 존재 유무**를 파악할 때 사용할 수 있다.
2. List 등과 달리 저장된 순서가 보장되지 않는다.
	- 저장 순서를 유지해야 한다면 JDK 1.4부터 제공하는 `LinkedHashSet`을 사용해야 한다.
3. null을 값으로 허용한다.

## HashSet의 사용법
HashSet 내부 코드를 보면 `HashMap`을 사용하여 구현되어 있는 것을 볼 수 있다.
### HashSet 생성
```java
// 타입을 지정
HashSet<String> animals1 = new HashSet<String>();

// 타입을 생략하여 사용 가능 -> 빈 HashSet 생성 시 사용
HashSet<String> animals2 = new HashSet<>();

// 초기 용량(Capacity) 설정
HashSet<String> animals3 = new HashSet<>(10);

// animal의 모든 값을 가진 HashSet 생성
HashSet<String> animals4 = new HashSet<>(animals1);

// 초기값 지정 가능
HashSet<String> animals5 = new HashSet<>(Arrays.asList("tiger", "lion", "fox"));
```

### HashSet 요소 값 추가
생성된 Hash에 `add()` 메소드를 호출하여 값을 추가 할 수 있다.
```java
HashSet<String> animals = new HashSet<>();
	animals.add("tiger");
	animals.add("lion");
	animals.add("fox");
```
>[!important] HashSet은 저장 순서가 보장되지 않기 때문에 특정 위치에 값을 추가할 수는 없다!

>[!note] 만약 입력되는 값이
>- HashSet 내부에 존재하지 않는다면 그 값을 HashSet에 추가하고 true를 반환한다.
>- HashSet 내부에 존재하면 false 를 반환한다.

### HashSet 크기 구하기
- `size()` 메소드를 사용하여 Hash의 크기를 구할 수 있다.
```java
HashSet<Integer> set = new HashSet<Integer>(Arrays.asList(1,2,3));

//set 크기 : 3
System.out.println(set.size());
```

### HashSet 요소 값 삭제
- `remove(value)`와 `clear()` 메소드를 사용하여 Hash 값을 제거할 수 있다.
```java
HashSet<Integer> set = new HashSet<Integer>(Arrays.asList(1,2,3));

// 값 1 제거
set.remove(2);

// 모든 값을 제거
set.clear();
```

>[!note] 만약 삭제 하려는 값이
>- HashSet 내부에 존재하면 그 값을 삭제하고 true를 반환한다.
>- HashSet 내부에 존재하지 않으면 false 를 반환한다.

### HashSet 요소 값 검색
- 원하는 값에 대해 `contains(value)` 메소드를 통해 Hash 내부에 존재하는 지 확인이 가능하다.
```java
HashSet<Integer> set = new HashSet<Integer> (Arrays.asList(1,2,3));

// set 내부에 값 1이 잆으면 true , 없으면 false 출력
System.out.println(set.contains(1));
```

### HashSet 요소 값 출력
- Set 컬렉션을 그냥 'print' 처리 할 경우 대괄호('[]')로 묶여 Set의 전체값이 출력된다.
- 때문에 전체 객체를 대상으로 한번씩 반복해서 가져오는 `반복자 (Iterator)` 를 사용해 출력해야 한다.
```java
HashSet<Integer> set = new HashSet<Integer> (Arrays.asList(1,2,3));

// 출력 결과 : [1,2,3]
System.out.println(set);

Integer iter = set.iterator();

//hasNext() : 가져올 객체가 있으면 true, 없으면 false 리턴
//next() : Iterator 에서 하나의 객체를 가져올 수 있는 메소드

while(iter.hasNext()){
	System.out.print(iter.next());
}
```

# 참고
[[JAVA] HashSet이란? & 사용법 정리](https://crazykim2.tistory.com/474) <br>
[[Java] 자바 HashSet 사용 방법](https://psychoria.tistory.com/780) <br>
[[Java] HashSet의 개념과 사용법 정리](https://velog.io/@acacia__u/hashSet) <br>

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