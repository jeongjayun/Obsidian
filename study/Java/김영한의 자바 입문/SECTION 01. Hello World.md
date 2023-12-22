# 인텔리제이 vs 이클립스
- 과거에는 이클립스를 많이 사용했지만 최근에는 빠른 속도와 편의성 때문에 인텔리제이를 주로 사용하는 추세다.

# OS
- 자바로 개발하는 대부분의 메이저 회사들은 Mac 사용
- 윈도우를 사용해도 무방함

# 인텔리제이 설정
- java : Oracle openjdk 21.0 ver

# 자바 프로그램 실행
## HelloJava

```java
public class HelloJava {
    public static void main(String[] args) {
        //main 메서드
        System.out.println("Hello Java");
    }
}
```

### public class HelloJava
- HelloJava를 클래스(class) 라고 함.
- 파일명과 클래스 이름이 같아야 한다.
- {} 블록을 사용해서 클래스의 시작과 끝을 나타낸다.

### public static void main(String[] args) {
- main 메서드.
- 자바는 main(String[] args) 를 찾아서 프로그램을 시작한다.
- {} 블록을 사용해서 메서드의 시작과 끝을 나타낸다.

### System.out.println("Hello Java");
- System.out.println() : 값을 콘솔에 출력하는 기능.
- "Hello Java" : 문자열을 사용할 때 "(쌍따옴표) 를 사용한다. 
- 자바는 문장이 끝날 때마다 ; 필수로 넣어 구분해줘야 한다.

#### 참고 : 괄호
- 소괄호 ()
- 중괄호  {}
- 대괄호 []

### 실행과정
1. HelloJava 프로그램 실행
2. 시작점인 main() 메서드를 실행
3. System.out.println(); 만나고 문자열 출력
4. main() 메서드의 {} 블록의 끝에서 프로그램 종료.

```java
public class HelloJava { // HelloJava 클래스의 범위 시작
    public static void main(String[] args) { // main() 메서드의 범위 시작
        System.out.println("Hello Java");
    } // main() 메서드의 범위 끝  
} // HelloJava 클래스의 범위 끝 
```

## 블록(block) 예시
- 블록({})이 시작되고 끝날 때마다 들여쓰기가 적용되어 있음.
	- 코드를 쉽게 구분
	- 이해하기 좋도록 돕는 관례
	- 블록이 중첩될 때마다 들여쓰기의 길이가 추가 됨.
- 들여쓰기는 보통 스페이스 4번 사용.
- 들여쓰기가 없어도 프로그램은 돌아가지만 가독성 떨어짐.

# 주석 (comment)
- 소스 코드가 복잡하다면 소스 코드에 대한 이해를 돕기 위해 설명을 적어두고 싶을 수 있다.
- 특정 코드를 지우지 않고 잠시 실행을 미뤄두고 싶을 수도 있다.
- 주석을 사용하면 주석이 있는 곳을 무시하고 동작한다.

## 주석의 종류
1. 한줄 주석 single line comment
	- // 기호로 시작함. 이 기호 이후의 모든 텍스트는 주석으로 처리.
2. 여러 줄 주석 multiple line comment 
	- '/*'로 시작하고 '*/' 로 끝난다. 이 사이의 모든 텍스트는 주석으로 처리한다.
