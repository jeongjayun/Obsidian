#Scanner #입출력 

>scanner, System.out.println(); 보다 속도 측면에서 훨씬 빠름.
>입력된 데이터가 바로 전달되지 않고 버퍼를 거쳐 전달되므로 **데이터 처리 효율성을 높이고 많은 양의 데이터를 처리할 때 유리**하다.

# 💡 사용 전 import 문
```java
//BufferedReader, BufferedWriter 사용하려면 아래 import 추가
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
```

# BufferdReader
> Scanner와 비슷하다.

```java
//how to use method
BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
String s = bf.readLine(); // String으로 데이터 받음
int i = Integer.parseInt(bf.readLine()); // Int로 형변환 필요
```

## readLine();
메서드 사용 시 <u>반환값을 String으로 고정</u>하기 때문에 **다른 형으로 받으려면 반드시 형변환**이 필요하다.
<font color="#c0504d">무조건 예외발생하기 때문에 try & cath 또는 throws IOException으로 처리</font>한다.

## throw 이용 시 
```java
//how to use thorw Exception
// (1) 클래스를 import 하기.
import java.io.IOException; 

// (2) main 클래스 옆에 throws IOException 추가하기. 

public static void main(String[] args) throws IOException {}
```

⭐️⭐️ 하지만 BufferedReader는 **Enter만 경계로 인식**하고 받은 데이터를 String으로 고정하기 때문에 입력받은 <u>데이터를 가공하는 작업이 필요한 경우가 많다</u>.

# BufferedWriter
> System.out.println(); 와 비슷

```java
//how to use method
BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out)); String s = "abcdefg"; //출력할 문자열
bw.write(s+"\n"); //버퍼에 있는 값 전부 출력
bw.flush(); //남아있는 데이터를 모두 출력시킴
bw.close(); //스트림을 닫음
```

⭐️ <span style="background:#fff88f">스트림을 꼭 닫아줘야</span> 한다.

# StringTokenizer
> readLine(); 으로 입력받은 데이터는 line(엔터)로만 나눠지기 때문에 공백단위로 데이터를 가공하려면 위의 메서드를 사용해 작업을 해줘야 한다.

```java
//how to use method
StringTokenizer st = new StringTokenizer(s);
//StringTokenizer 인자값에 입력 문자열 넣음
int a = Integer.parseInt(st.nextToken()); // 첫번째 호출
int b = Integer.parseInt(st.nextToken()); // 두번째 호출

String array[] = s.split(" "); //공백마다 데이터 끊어서 배열에 넣음
```

# EOF (End Of File)개념
> 입력에서 더 이상 읽을 수 있는 데이터가 없을 때
> = null 을 뜻한다.

처리하는 방법이 여러가지 있으나
## 1) Scanner
	Scanner의 메소드들의 경우 더이상 읽을 데이터가 없으면 NoSuchElementException을 던지게 된다.
	던져진 예외의 경우에는 hasNext()메소드를 사용하여 처리한다.
	**EOF의 경우 false반환, 값이 있는 경우 true를 반환한다.**

```java
Scanner sc = new Scanner(System.in);
while(sc.hasNext()){
	// 입력되는 형식에 따라 달리 작성
}
```
## 2) BufferdReader
	null을 반환한다.
	(str=br.readLine())≠null 을 사용하여 처리해준다.
	**EOF일 경우 false 반환, 값이 있는 경우 ture 반환한다.**

```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
String str;
while((str = br.readeLine() != null) {
	// 입력되는 형식에 따라 작성
}


	// 입력의 끝에 enter 를 한번 더 입력하면 그 입력을 EOF로 판별하여 처리한다.
while((str = br.readLine()) != null && !str.isEmpty()){

}
```