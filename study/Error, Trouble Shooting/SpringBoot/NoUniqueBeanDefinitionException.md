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

![](https://i.imgur.com/BKhec0T.png)
AppConfig.class 에서 @Bean 등록 제거함.<br>
@Component 와 @Bean 애노테이션 사용함으로 스프링빈이 2개가 등록됨.

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

새로운 오류가 나오고 아까 전엔 통과했던 싱글톤테스트 오류가 발생함 ...

# 해결