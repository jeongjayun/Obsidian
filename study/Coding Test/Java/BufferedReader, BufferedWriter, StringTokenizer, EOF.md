>scanner, System.out.println(); 보다 속도 측면에서 훨씬 빠름.
>입력된 데이터가 바로 전달되지 않고 버퍼를 거쳐 전달되므로 데이터 처리 효율성을 높이고 많은 양의 데이터를 처리할 때 유리하다.

# BufferdReader
> Scanner와 비슷하다.

```java
//how to use method
BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
String s = bf.readLine(); // String으로 데이터 받음
int i = Integer.parseInt(bf.readLine()); // Int로 형변환 필요
```

⭐️ **readLine()**;
메서드 사용 시 <u>반환값을 String으로 고정</u>하기 때문에 **다른 형으로 받으려면 반드시 형변환**이 필요하다.
<font color="#c0504d">무조건 예외발생하기 때문에 try & cath 또는 throws IOException으로 처리</font>한다.


```java
throw 이용 시

(1) 클래스를 import해주어야 한다. 

import java.io.IOException; 

(2) main 클래스 옆에 throws IOException를 작성한다. 

public static void main(String[] args) throws IOException {}
```

⭐️⭐️ 하지만 BufferedReader는 **Enter만 경계로 인식**하고 받은 데이터를 String으로 고정하기 때문에 입력받은 <u>데이터를 가공하는 작업이 필요한 경우가 많다</u>.

# BufferedWriter