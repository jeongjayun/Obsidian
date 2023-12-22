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
- 참고로 변수의 값은 반복해서 읽을 수 있다. 읽어서 값이 없어지진 않는다.

# 변수 값 변경
