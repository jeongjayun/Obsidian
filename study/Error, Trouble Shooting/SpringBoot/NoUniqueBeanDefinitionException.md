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
### 에러 코드 확인
>[!bug] Caused by: org.springframework.beans.factory.**NoUniqueBeanDefinitionException**.

# 해결
