
```text
***************************
APPLICATION FAILED TO START
***************************

Description:

Parameter 0 of constructor in hello.core.member.MemberServiceImpl required a single bean, but 2 were found:
	- memoryMemberRepository: defined in file [/Users/jeongjayun/workspace/IntelliJ-workspace/core/out/production/classes/hello/core/member/MemoryMemberRepository.class]
	- memberRepository: defined by method 'memberRepository' in class path resource [hello/core/AppConfig.class]


Action:

Consider marking one of the beans as @Primary, updating the consumer to accept multiple beans, or using @Qualifier to identify the bean that should be consumed
```

# 에러 상황
- [김영한 핵심원리 강의](https://www.inflearn.com/course/lecture?courseSlug=스프링-핵심-원리-기본편&unitId=55374&category=questionDetail&tab=community&q=979646) 수강하며 따라하던 중 오류 발생한 지점을 김영한님 따라 수정했음에도 계속 에러 발생해서 확인하니 다른 에러였음.
## 에러 코드 확인
>[!bug] Caused by: org.springframework.beans.factory.**NoUniqueBeanDefinitionException**.


## 내가 작성한 코드 확인
```java
package hello.core.member;  
  
import org.springframework.stereotype.Component;  
  
import java.util.HashMap;  
import java.util.Map;  
  
@Component  
public class MemoryMemberRepository implements MemberRepository {  
    private static Map<Long, Member> store = new HashMap<>();  
    //hashmap = 동시성 이슈 있음  
  
    @Override  
    public void save(Member member) {  
        store.put(member.getId(), member);  
    }  
  
    @Override  
    public Member findeById(Long memberId) {  
        return store.get(memberId);  
    }  
}
```

```java
package hello.core;  
  
import hello.core.discount.DiscountPolicy;  
import hello.core.discount.RateDiscountPolicy;  
import hello.core.member.*;  
import hello.core.order.OrderService;  
import hello.core.order.OrderServiceImpl;  
import org.springframework.context.annotation.Bean;  
import org.springframework.context.annotation.Configuration;  
  
@Configuration // 설정정보  
public class AppConfig {  

    @Bean(name = "memberService")  
    public MemberService memberService() {  
        System.out.println("call AppConfig.memberService");  
        return new MemberServiceImpl(memberRepository());  
    }  
  
    // 빈 이름  
    // 메서드 이름을 사용한다. 위처럼 name ="" 으로 이름 지정해줄 수 있음.  
    // 빈 이름은 항상 다른 이름을 부여해야 한다. 같은 이름을 부여하면 다른 빈이 무시되거나 기존 빈을 덮어버리는 등 설정에 따라 오류가 발생한다. 실무에서는 단순하고 명확하게 개발해야 한다.  
  
    @Bean  
    public MemberRepository memberRepository() {  
        System.out.println("call AppConfig.memberRepository");  
        return new MemoryMemberRepository();  
    }  
  
    @Bean  
    public OrderService orderService(){  
        System.out.println("call AppConfig.orderService");  
        return new OrderServiceImpl(memberRepository(), discountPolicy());}  
  
    @Bean  
    public DiscountPolicy discountPolicy(){  
        System.out.println("call AppConfig.discountPolicy");  
//        return new FixDiscountPolicy();  
        return new RateDiscountPolicy();  
    }  
}
```

### 시도 1
![](https://i.imgur.com/BKhec0T.png)
AppConfig.class 에서 @Bean 등록 제거함.<br>
@Component 와 @Bean 애노테이션 사용함으로 스프링빈이 2개가 등록됨.

### 시도 2
Action을 따라 **@Primary 어노테이션**을 둘 중에 하나에 적용했더니 아래와 같은 코드 발생.

```text
***************************
APPLICATION FAILED TO START
***************************

Description:

Parameter 1 of constructor in hello.core.order.OrderServiceImpl required a single bean, but 2 were found:
	- rateDiscountPolicy: defined in file [/Users/jeongjayun/workspace/IntelliJ-workspace/core/out/production/classes/hello/core/discount/RateDiscountPolicy.class]
	- discountPolicy: defined by method 'discountPolicy' in class path resource [hello/core/AppConfig.class]


Action:

Consider marking one of the beans as @Primary, updating the consumer to accept multiple beans, or using @Qualifier to identify the bean that should be consumed
```
새로운 오류가 나오고 전엔 통과했던 싱글톤 테스트 오류가 발생함 ...

### 시도 3
rateDiscountPolicy, discountPolicy 중에 rateDiscountPolicy에 `@Primary` 어노테이션을 적용했다. 

# 해결
![](https://i.imgur.com/JpP7xyr.png)

# 참고
[[Spring] 스프링 조회한 빈(Bean)이 2개 이상인 경우 문제 해결 방법](https://ittrue.tistory.com/231) <br>
[중복 오류 - 인프런](https://www.inflearn.com/questions/954940/중복-오류)

# 느낀점
스프링 자체적으로 싱글톤을 유지하기 위한 기능이 있다고 백번 설명 듣는 것보다 이렇게 직접 오류 마주하니 훨씬 와닿는다.