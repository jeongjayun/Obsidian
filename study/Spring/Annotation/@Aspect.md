#AOP  [[7. AOP]]

>[!info] AOP 사용법 <Br>
>	1. XML 사용
>	2. 어노테이션 사용

# pom.xml 사전 설정
```xml
<dependency>
    <groupId>org.aspectj</groupId>
    <artifactId>aspectjweaver</artifactId>
    <version>1.8.0</version>
</dependency>
```

AOP 사용 전 pom.xml의 dependencies에 `AspectJ Weaver` 라이브러리 추가.

# Advice 어노테이션
| 어노테이션       | 설명                                                                          |
| ---------------- | ----------------------------------------------------------------------------- |
| @Before          | 메소드가 실행되기 이전에 실행됨.                                              | 
| @After           | 메소드의 종료 후 무조건 실행됨.(Try-catch에서 **finally처럼**)                    |
| @After-returning | 메소드가 서공적으로 완료되고 리턴한 다음에 실행됨.                            |
| @After-throwing  | 메소드 실행 중 예외가 발생하면 실행됨.(Try-catch에서 **catch처럼**)               |
| @Around          | 메소드 호출 자체를 가로채서 메소드 실행 전 후에 처리할 로직을 삽입할 수 있다. |

Advice 의 종류와 사용법은 5가지가 있는데 이를 사용하기 위해선 Pointcut표현식으로 적용 범위를 적용해주어야 한다.

```java
@Component
@Aspect
public class SpringAspect {
	// -1-
	@Before("execution(* aop *.*(..)")
	public void aop1() {}
	
	// -2-
	private final String pointcut = "execution(* aop *.*(..)";
	@Before(pointcut)
	public void aop2() {}
	
	// -3-
	@Pointcut("execution(* aop *.*(..)")
	private void method() {} 
	
	@Before("method()")
	public void aop3() {}
}
```

# AOP 사용 예제
- AOP 사용 예제 주제로 메소드 실행 시 실행 시간을 측정하는 기능
- 실행시간을 측정하기 위해선 메소드 실행 전과 실행 후를 하나의 변수에 담아 측정해야 하기 때문에 @Around Advice 사용

```java
@Component
@Aspect
public class SpringAspect {
	@Around("execution(* aop_obj.*.*(..))")
	public void timer(ProceedingJoinPoint joinPoint) throws Throwable {
		System.out.println("[Around] 시작");
		StopWatch sw = new StopWatch();
		
		sw.start();
		joinPoint.proceed(); // 메소드 시작
		sw.stop();
		
		System.out.println("[Around] 메소드 이름 : "+joinPoint.getSignature().getName());
		System.out.println("[Around] 메소드 첫번째 파라미터 : "+joinPoint.getArgs()[0]);
		System.out.println("[Around] 메소드 소요 시간 : "+sw.getTotalTimeMillis());
	}
}
```

## @Around("execution(* aop_obj.*.*(..))")
- 포인트컷 표현식
- Around 어드바이스는 ProceedingJoinPoint를 파라미터로 받아 실행할 메소드의 시점을 조절하거나, 각종 정보들을 받아올 수 있습니다.
