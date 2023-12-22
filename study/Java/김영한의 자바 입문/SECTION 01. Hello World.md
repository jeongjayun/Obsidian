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
- 자바는 문장이 끝날 때마다 ; 필수로 넣어 구분해줘야 한다.