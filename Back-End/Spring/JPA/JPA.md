# JPA

## JPA란?

JPA 자바 ORM(Object Relational Mapping) 기술에 대한 표준 명세를 뜻한다.

## ORM이란?

ORM 기술은 객체와 테이블을 연결하는 기술을 뜻하며, 기술적으로는 애플리케이션 객체를 RDB 테이블에 자동으로 영속화 해주는 것이라고 생각하면 된다.

## 장점
- SQL문이 아닌 Method를 통해 DB를 조작할 수 있어 개발자가 비즈니스 로직에만 집중할 수 있게 된다.

- 객체지향적인 코드 작성이 가능하다.

- 기존에 DB에서 다른 DB로 변경하여도 ORM이 알아서 해주기 떄문에 쿼리를 수정하지 않아도 된다.

## 단점

- 프로젝트의 큐모가 크고 복잡하여 설계가 잘못된 경우 속도 저하 및 일관성을 무너뜨리는 문제가 있다.

- 복잡한 쿼리는 별로의 튜닝을 하여 사용해야하므로 SQL문을 써야할 수 있다.

## JPA(Java Persist API)

- java 진영에서 ORM 기술 표준으로 사용하는 인터페이스 모음
-java 애플리케이션에서 관계형 데이터베이스를 사용하는 방식을 정의한 인터페이스 
- 인터페이스이므로 Hirbernate, OpenAPI 등이 JPA를 구현함

## Hibernate란?

![image](https://github.com/minjun7283/TIL/assets/107666764/007a59d1-ed32-43d3-988f-b089ce91d188)
 -> 출처 : 구글 검색

- Hibernate는 JPA의 구현체이며, 대중적으로 많이 사용되는 JPA 구현체 중 하나이다.
- Hibernate 외 다른 구현체들은 EclipseLink, DataNucleus 등이 있다.
- 만약 JPA를 구현한 구현체가 마음에 들지 않는다면 개발자가 직접만들 수도 있다.
- Hibernate는 내부적으로 JDBC를 이용한 관계형 데이터베이스와 커넥션을 맺고 상호작용한다.

## Spring Data JPA란?

Spring Data JPA는 JPA를 한 단계 더 추상화시킨 Repository 인터페이스를 제공한다. 
이러한 Spring Data JPA는 Hibernate와 같은 JPA 구현체를 사용하여 JPA를 사용하게 된다.
Spring Data JPA를 사용하면 더 간단하게 데이터에 접근이 가능해진다.

---------------------------

![image](https://github.com/minjun7283/TIL/assets/107666764/cd85d3b8-3005-43e3-b268-bca85d1b8986)

정리하자면 JPA는 자바 진영의 ORM 기술에 대한 API표준 명세이고, 
Hibernate는 JPA의 구현체이며, Hibernate는 내부적으로 JDBC를 이용한다.
Spring Data JPA는 JPA를 사용하기 쉽게 스프링에서 제공하는 모델로 내부적으로는 JPA 구현체를 사용한다.
