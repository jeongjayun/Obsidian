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
- `{}` 블록을 사용해서 클래스의 시작과 끝을 나타낸다.

### public static void main(String[] args) {
- main 메서드.
- 자바는 `main(String[] args)` 를 찾아서 프로그램을 시작한다.
- `{}` 블록을 사용해서 메서드의 시작과 끝을 나타낸다.

### System.out.println("Hello Java");
- `System.out.println()` : 값을 콘솔에 출력하는 기능.
- "Hello Java" : 문자열을 사용할 때 `"(쌍따옴표)` 를 사용한다. 
- 자바는 문장이 끝날 때마다 ; 필수로 넣어 구분해줘야 한다.

#### 참고 : 괄호
- 소괄호 ()
- 중괄호  {}
- 대괄호 []

### 실행과정
1. HelloJava 프로그램 실행
2. 시작점인 main() 메서드를 실행
3. `System.out.println();` 만나고 문자열 출력
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
	- `//` 기호로 시작함. 이 기호 이후의 모든 텍스트는 주석으로 처리.
2. 여러 줄 주석 multiple line comment 
	- `'/*'`로 시작하고 `'*/'` 로 끝난다. 이 사이의 모든 텍스트는 주석으로 처리한다.

```java
public class CommentJava {
    public static void main(String[] args) {
        System.out.println("hello java1"); //hello java1 을 출력합니다.
        // System.out.println("hello java2"); //hello java2 을 출력합니다.
        /*System.out.println("hello java3");
        System.out.println("hello java4");*/
    }
}
```

# 자바란?
## 자바 표준 스펙
### 자바 표준 스펙과 구현
![[Pasted image 20231222160437.png]]
자바는 표준스펙과 구현으로 나눌 수 있다.
- 자바 표준 스펙
	- 자바는 이렇게 만들어야 한다는 설계도, 문서.
	- 표준 스펙을 기반으로 여러 회사에서 실제 작동하는 자바를 만든다.
	- 자바 표준 스펙은 자바 커뮤니티 프로세스를 통해 관리한다.
- 다양한 자바 구현
	- 여러 회사에서 자바 표준 스펙에 맞추어 실제 작동하는 자바 프로그램을 개발한다.
	- 각각 장단점이 있음. (ex, Aamzon Corretto = AWS에 최적화 되어있음)
	- 각 회사들은 대부분 다양한 OS에서 작동하는 버전의 자바도 함께 제공함.
## 변경이 용이
![[Pasted image 20231222160736.png]]

## 컴파일과 실행
![[Pasted image 20231222160802.png]]
자바 프로그램은 컴파일과 실행단계를 거침
- Hello.java와 같은 자바 소스코드를 개발자가 작성한다.
- 자바 컴파일러를 사용하여 소스 코드를 컴파일한다.
	- 자바가 제공하는 javac 프로글매을 사용한다.
	- .java -> .class 파일이 생성된다.
	- 자바 소스 코드를 바이트 코드로 변환하여 자바 가상 머신에서 더 빠르게 작동하기 위해 최적화하고 오류를 수정한다.
- 자바 프로그램을 실행한다.
	- 자바가 제공하는 java라는 프로그램을 사용한다.
	- 자바가상머신(JVM)이 실행되면서 프로그램이 작동한다.

## 자바와 운영체제 독립성
### 일반적인 프로그램
- 일반적인 프로그램은 다른 운영체제에서 실행할 수 없음.
### 자바 프로그램
![[Pasted image 20231222161627.png]]
- 자바 프로그램은 자바가 설치된 모든 OS에서 실행할 수 있음.
- 자바 개발자는 특정 OS에 맞추어 개발하지 않아도 됨.

### 자바 개발과 운영환경
![[Pasted image 20231222162148.png]]
- 개발할 때 자바와 서버에서 실행할 때 다른 자바를 사용할 수 있다.
- 개발자들은 개발의 편의를 위해 윈도우나 Mac OS를 주로 사용한다.
- 서버는 주로 리눅스 사용 / 만약 AWS 사용한다면 아마존Corretto 자바를 AWS 리눅스 서버에 설치하면 된다.
- 자바의 운영체제 독립성 덕분에 각각의 환경에 맞추어 자바를 설치하는 것이 가능하다.