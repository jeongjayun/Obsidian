# StringBuilder 사용해야 하는 이유
```java
String str1 = "Hello ";
String str2 = "Java";
str 1 += str2;

System.out.println(str1); //"Hello Java"
```

String 객체가 2개 있을 때 `str1 + str2` 하면 새로운 String 을 생성할 수 있다.<br>
**String**은 소위 **불변(immutable) 객체로 한 번 생성되면 변경할 수 없다**.<br>

`+` 연산자를 사용하여 <u>문자열을 연결하면 연결할 때마다 새로운 문자열 객체가 생성된다</u>는 것을 의미한다. 또한 <u>이전에 있던 문자열은 JVM의 GC가 처리</u>하게 된다. String 객체와 String 객체를 더하는 것은 메모리의 할당과 해제를 발생시켜 더하는 연산이 많아지면 성능적으로 좋지 않다.

# StringBuilder 의 등장
위와 같은 문제점을 해결하기 위해 `StringBuilder` 가 등장했다. StringBuilder 는 String 과 다르게 **mutable한 성질**을 가지고 있어 **값이 변할 수 있다**는 장점이 있다. 또 StringBuilder는 String과 문자열을 더할 때마다 새로운 객체를 생성하는 것이 아니라 <span style="background:#fff88f">기존의 데이터에 더하는 방식을 사용하기 때문에 속도도 빠르고 상대적으로 부하가 적다</span>. 따라서 긴 문자열을 더해야 하는 상황이 발생할 경우에는 StringBuffer 또는 StringBuilder를 적극적으로 사용해보자.

>[!note] StringBuffer, StringBuilder의 차이 : 멀티스레드 환경에서 Thread-safe 여부가 다르다.
>StringBuffer는 Thread-safe 하므로 여러 쓰레드에서 동시에 해당 문자열에 접근한다면 사용을 고려하고, 그렇지 않다면 StringBuilder를 사용하는 것이 성능에 유리하다. (성능과 thread-safe는 반비례)

> 정리
> 1. 문자열 변경이 빈번하지 않는다 -> String
> 2. 문자열이 빈번하게 변경되면서 멀티쓰레드 환경 -> StringBuffer
> 3. 문자열이 빈번하게 변경되면서 멀티쓰레드 환경이 아니라면 -> StringBuilder

>[!note] Thread-safe 스레드 안전
>멀티 스레드 프로그래밍에서 일반적으로 어떤 함수나 변수, 혹은 객체가 여러 스레드로부터 동시에 접근이 이루어져도 프로그램의 실행에 문제가 없음. 하나의 함수가 한 스레드로부터 호출되어 실행 중일 때, 다른 스레드가 그 함수를 호출하여 동시에 함께 실행되더라도 각 스레드에서의 함수의 수행 결과가 올바르게 나오는 것으로 정의한다. [[OS] Thread Safe란? — 곰팡이 먼지연구소](https://gompangs.tistory.com/entry/OS-Thread-Safe란)

# 생성자
**StringBuilder** (java.lang.StringBuilder)
1. 기본 생성자
	```java
	StringBuilder sb = new StringBuilder();
	```
2. int size 값을 인자로 하는 생성
	```java
	StringBuilder sb = new StringBuilder(20);
	// int 타입의 값으로 Buffer 의 사이즈를 지정한다.
	```
3. String 문자열을 인자로 하는 생성자
	```java
	StringBuilder sb = new StringBuilder("aaa");
	```

# 주요 메소드
## 문자열을 추가
```java
StringBuilder sb = new StringBuilder();
sb.append("abd");
sb.append(4).append("\n");
```


# 참고
[[Java] StringBuilder 사용법과 주요 메소드](https://myeongju00.tistory.com/61)