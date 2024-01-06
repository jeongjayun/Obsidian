# StringBuilder 사용해야 하는 이유
```java
String str1 = "Hello ";
String str2 = "Java";
str 1 += str2;

System.out.println(str1); //"Hello Java"
```

String 객체가 2개 있을 때 `str1 + str2` 하면 새로운 String 을 생성할 수 있다.<br>
**String**은 소위 **불변(immutable) 객체로 한 번 생성되면 변경할 수 없다**.<br>
+ 연산자를 사용하여 문자열을 연결하면 연결할 때마다 새로운 문자열 객체가 생성된다는 것을 으