# Var1
```java
package variable;  
  
public class Var1 { // 클래스 이름은 관례상 첫글자는 대문자  
    public static void main(String[] args) {  
        System.out.println(10);  
        System.out.println(10);  
        System.out.println(10);  
    }  
}
```

## 패키지 package
- 자바 파일을 구분하기 위한 폴더
- variable 패키지 생성 -> 해당 패키지에 들어가는 파일 첫줄에 `package variable;` 와 같이 소속된 패키지를 선언해줘야 한다.
- 자바 파일이 위치하는 패키지와 `package variable;`  선언 위치가 같아야 한다.

## Var1
```java
package variable;  
  
public class Var1 { // 클래스 이름은 관례상 첫글자는 대문자  
    public static void main(String[] args) {  
        System.out.println(20); // 변경 10->20       
        System.out.println(20); // 변경 10->20        
        System.out.println(20); // 변경 10->20    }  
}
```

**변수 : 변할 수 있는 수**

## Var2
```java
package variable;  
  
public class Var2 {  
    public static void main(String[] args) {  
        int a; // 변수 선언  
//        a = 10; // 변수 초기화  
        a = 20; // 변수 변경  
  
        System.out.println("a = " + a);  
        System.out.println("a = " + a);  
        System.out.println("a = " + a);  
    }  
}
```

### 변수 선언
`int a`
- 숫자 정수(integer)를 보관할 수 있는 이름이 `a`라는 데이터 저장소를 만든다. = 변수라고 함.
- 이제 변수 a에는 integer 타입만 보관할 수 있다.

### 변수에 값 대입
`a = 10`
- 자바에서` = `은 오른 쪽에 있는 값을 왼쪽에 저장한다는 뜻.
- 수학에서 이야기하는 `두 값이 같다(equals)`와는 다른 뜻이다.
- 숫자를 보관할 수 있는 데이터 저장소 a 에 10을 저장한다.
- <u>선언한 변수에 처음으로 값을 대입해서 저장하는 것</u>을 `변수 초기화`라고 한다.

### 변수 값 읽기
`System.out.println(a)`
- 변수에 저장되어 있는 값을 읽어서 사용하는 방법 : 변수 이름을 적어준다.
- 변수 a 에 10이 들어가 있다면 자바는 실행 시점에 변수의 값을 읽어서 사용한다.
	- `System.out.println(a)` // 변수 a의 값을 읽음
	- `System.out.println(10)` // a의 값인 10으로 변경, 숫자 10 출력
- 참고로 변수의 값은 반복해서 읽을 수 있다. 읽어서 값이 없어지지 않는다.

# 변수 값 변경
## Var3
```java
package variable;  
  
public class Var3 {  
    public static void main(String[] args) {  
        int a; // 변수 선언  
        a = 10; // 변수 초기화  
        System.out.println("a = " + a);  
        a = 50; // 변수 값 변경   
System.out.println("a = " + a);  
    }  
}
```
프로그램은 한 줄씩 순서대로 실행된다.
참고로 변수의 값은 변경하면 변수에 들어있던 기존 값은 삭제됨.

# 변수 선언과 초기화
## 변수 선언
변수를 선언하면 컴퓨터의 메모리 공간을 확보하여 데이터를 저장할 수 있다.

### Var4
```java
package variable;  
  
public class Var4 {  
    public static void main(String[] args) {  
        int a;  
        int b;  
          
        int c, d;  
    }  
}
```

## 변수 초기화
### Var5
```java
package variable;  
  
public class Var5 {  
    public static void main(String[] args) {  
        // 1. 변수 선언, 초기화 각각 따로  
        int a;  
        a = 1;  
        System.out.println("a = " + a);  
  
        // 2. 변수 선언과 초기화를 한번에  
        int b = 2;  
        System.out.println("b = " + b);  
  
        // 3. 여러 변수를 한번에 선언, 초기화  
        int c = 3, d = 4, e = 5;  
        System.out.println("c = " + c);  
        System.out.println("d = " + d);  
        System.out.println("e = " + e);  
    }  
}
```
**변수는 초기화를 해야한다.**

### Var6
```java
package variable;  
  
public class Var6 {  
    public static void main(String[] args) {  
        int a;  
        System.out.println("a = " + a); // 컴파일 오류 발생
    }  
}
```

`java: variable a might not have been initialized`
변수 초기화 되지 않으면 오류 발생함.
WHY ? 컴퓨터에서 메모리는 여러 시스템이 함께 사용하는 공간으로 어떤 값들이 계속 저장된다. 변수를 선언하면 메모리상의 어떤 공간을 차지하고 사용하는데 기존에 어떤 값이 있었는지 아무도 모르면 이상한 값이 출력될 수 있다. -> 이런 문제를 예방하기 위해 변수 초기화 하도록 강제 된다.

> **참고** : 지금 학습 중인 변수 = 지역변수, 
> 지역변수는 개발자가 직접 초기화를 해줘야 한다.<br>
> 나중에 배울 전역변수와 인스턴스 변수는 자바가 자동으로 초기화를 진행해준다.
 
>**참고** : 컴파일 에러는 자바 문법에 맞지 않았을 때 발생하는 에러.<br>
>컴파일 에러 = 오류를 빨리 명확하게 찾을 수 있어 좋은 에러.<br>
>런타임 에러 = 오류를 찾기 어려워 나쁜 에러.

# 변수 타입 1
데이터를 다루는 종류에 따라 다양한 타입이 존재함.
## Var7
```java
package variable;  
  
public class Var7 {  
    public static void main(String[] args) {  
        int a = 100; //정수  
        double b = 10.5; //실수  
        boolean c = true; //boolean : true / false 입력 가능  
        char d = 'A'; // 문자 하나  
        String e = "Hello Java"; // 문자열, 문자열을 다루기 위한 특별한 타입  
  
        System.out.println("a = " + a);  
        System.out.println("b = " + b);  
        System.out.println("c = " + c);  
        System.out.println("d = " + d);  
        System.out.println("e = " + e);  
    }  
}
```

## 변수 타입의 예
- int
- double
- boolean : 참과 거짓을 판단하는 곳에서 사용.
- char
- String : 문자열을 다루는 특별한 타입.

## 자신의 타입에 맞는 데이터 사용
- 타입이 맞지 않는 값이 할당되면 컴파일 에러가 발생함.

## 리터럴
코드에서 개발자가 직접 적은 `100, 10.5, true, A, Hello Java` 를 프로그램 용어로 리터럴이라고 함.
변수의 값은 변할 수 있지만 리터럴은 개발자가 직접 입력한 값으로 변하지 않는다. 그래서 보통 변수에 리터럴을 담아서 사용한다.

# 변수타입 2
## 숫자타입 = Var8
```java
package variable;  
  
public class Var8 {  
    //정수  
    byte b=127; // -128 ~ 127  
    short s = 32767; // -32768 ~ 32767  
    int i = 2147383647; // -21474683 ~ 2147483647 (20억)  
    long l = 9223372036854775807L; // .... 숫자 끝에 L 꼭 붙여서 구분.  
  
    //실수  
    float f = 10.0f; // f를 붙여줘야 함  
    double d = 10.0; // float 보다 double 이 범위가 더 크다.  
    //float 보다 double 이 정밀도가 높다.
}
```
- 숫자가 클수록 메모리 공간을 많이 차지한다.

### 리터럴 타입 지정
- 정수 리터럴은 int 를 기본으로 사용.