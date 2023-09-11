# Fetch Type이란?

JPA가 하나의 Entity를 조회할 떄, 연관관계의 객체들을 어떻게 가져올지를 결정하는 값을 의미한다.

## 즉시 로딩 (Eager Loading)  


Entity를 조회할 떄, 연관관계에 있는 Entity를 조인(join)을 통해 함께 조회하는 방식
- Entity A를 조회시 연관된 Entity B도 불러온다.
- 실제 Entity를 멥핑한다.
- join을 사용해 한번에 불러온다.
- 쿼리가 한번만 나간다.

`즉 데이터를 조회할 떄 연관된 모든 객체의 데이터까지 가져온다.`

## 지연 로딩 (Lazy Loading)
자신과 연관된 Entity를 실제로 사용할 때 연관된 Entity를 조회(SELECT)하는 방식

- Entity A를 조회시 연관되어 있는 Entity B를 한번에  불러오지는 않는다.
- 프록시를 멥핑하고 실제 Entity B를 조회하는 쿼리가 나간다.
- 쿼리는 두 번 나간다. A를 조회시 한번 B를 조회시 한번 

`즉 필요한 순간에만 연관된 객체의 데이터를 불러옴`

## 즉시 로딩 예시
```java
Public class Order{

    @Id @GenerateValue
    private Long id;

    @ManyToOne
    @JoinColunm(name = member_id)
    private Member member;
}
```
(코드는 대충 작성하였다.)
이러한 Order Entity를 불러오면 member에 있는 모든 데이터도 같이 불러와진다.

## 지연 로딩 예시

```java
Public class Order{

    @Id @GenerateValue
    private Long id;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColunm(name = member_id)
    private Member member;
}
```

@ManyToOne에 FetchType을 Lazy로 설정해주면 연관관계로 설정된 Member의 데이터는 불러와지지 않는다.


## 즉시 로딩(Eager Loading)과 지연 로딩(Lazy Loading)의 장단점

- 즉시 로딩
    - 장점
        - 연관된 모든 엔티티를 불러올 수 있음
    - 단점 
        - 불필요한 join으로 성능저하가 일어날 수 있음

- 지연 로딩
    - 장점
        - 다른 접근 방식보다 빠른 초기의 로딩 시간
        - 다른 접근 방식에 비해 적은 메모리 사용
    - 단점
        - 초기화가 지연되면 원치않는 순간 성능저하가 벌어질 수 있음