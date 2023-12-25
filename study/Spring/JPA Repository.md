#JPA #JPARepository [[6. 스프링 DB 접근 기술]]
# JPA 정의
자바 객체를 관계형 데이터 베이스에 영속적으로 저장하고 조회할 수 있는 ORM 기술에 대한 표준 명세를 의미함. JPA를 통해 개발자는 SQL쿼리를 작성하지 않고도 객체를 통해 데이터베이스를 조작할 수 있으며, 객체 지향적인 코드 작성과 유지 보수성이 향상된다. Entity 클래스를 작성한 후 Repository 인터페이스를 생성해야한다.

# JPA Repository
> package: org.springframework.data.jpa.repository

Spring Data JPA에서 제공하는 인터페이스 중 하나로, JPA를 사용하여 데이터베이스를 조작하기 위한 메서드들을 제공한다. JPARepository 인터페이스를 상속받는 인터페이스를 정의하면, 해당 인터페이스를 구현하는 클래스는 JPA에서 제공하는 메서드들을 사용할 수 있다.

**데이터베이스의 추가, 조회, 수정, 삭제의 findAll(), findById(), save() 등의 제공되는 메서드들 이용**하여 쉽고 간편하게 CRUD 조작을 할 수 있다. 즉, JpaRepository를 사용하면, 복잡한 JDBC(Java DataBase Connectivity) 코드를 작성하지 않아도 간단하게 DB와의 데이터 접근 작업을 처리할 수 있음.

**JPARepository 인터페이스는 제네릭 타입을 사용**함. Entity클래스와 복합키를 사용하고 있다면 해당 Entity의 ID클래스를 명시한다. 이를 통해 해당 인터페이스를 상속받는 구현체는 Entity 클래스와 ID클래스에 대한 정보를 알고 런타임 시점에 적절한 쿼리를 생성하고 실행할 수 있다.

## JPA 사용법
### 1. Entity 클래스 정의 
```java
@Getter @Setter
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private Integer age;
}
```
###  2. JpaRepository 인터페이스 상속받는 인터페이스 생성.
```java
public interface UserRepository extends JpaRepository<User, Long> {

    @Query("SELECT u FROM User u WHERE u.age >= :age")
    List<User> findByAgeGreaterThanEqual(@Param("age") Integer age);
}
```

### 3. 스프링 빈 등록
- JpaRepository를 사용하여 데이터 액세스를 수행하는 EntityManager가 필요하므로, JpaRepository를 사용하는 클래스는 빈으로 등록되어야 한다.
```java
@Service
public class UserService {
    @Autowired
    private UserRepository userRepository;
    // ...
}
```

### 4.JPARepository method 사용
- JPARepository 인터페이스에 정의된 메서드를 호출하거나 구현한 메서드를 호출한다.
```java
@Service
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public User saveUser(User user) {
        return userRepository.save(user);
    }

    public List<User> getAllUsers() {
        return userRepository.findAll();
    }

    public Optional<User> getUserById(Long id) {
        return userRepository.findById(id);
    }

    public void deleteUser(Long id) {
        userRepository.deleteById(id);
    }
    public List<User> getUsersByAge(Integer age) {
        return userRepository.findByAgeGreaterThanEqual(age);
    }
}
```
