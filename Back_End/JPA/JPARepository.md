## 1. 개념
- JPARepository는 JPA에서 제공하는 메서드를 사용할 수 있도록 도와줘서 **자동으로 DB쿼리를 처리할 수 있도록 하는 인터페이스**다.
- JPARepository는 CrudRepository, ListCrudRepository등 **여러 리포지토리 인터페이스를 상속**받는데,  
  그 덕에 findById(), findAll() 등 여러 메서드를 사용할 수 있어서 일반적으로 사용된다.

## 2. 사용방법
일반적인 구조는  
(예시)
```
public interface UserRepository extends JPARepository<User, Long> {}
```
이런 방식이다.

JPARepository의 제네릭 타입에 User와 Long이 있는걸 볼 수 있는데 각각,  
User는 Repository가 다룰 **Entity 클래스**,  
Long은 해당 Entity 클래스에서의 **기본키 타입**을 의미한다.
