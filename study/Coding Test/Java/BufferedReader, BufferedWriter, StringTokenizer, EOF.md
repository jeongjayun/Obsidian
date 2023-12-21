>scanner, System.out.println(); 보다 속도 측면에서 훨씬 빠름.
>
>입력된 데이터가 바로 전달되지 않고 버퍼를 거쳐 전달되므로 데이터 처리 효율성을 높이고 많은 양의 데이터를 처리할 때 유리하다.

# BufferdReader
> Scanner와 비슷하다.

```java
//how to use method
BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
String s = bf.readLine(); // String으로 데이터 받음
int i = Integer.parseInt(bf.readLine()); // Int로 형변환 필요
```