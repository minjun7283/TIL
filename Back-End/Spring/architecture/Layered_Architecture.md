# Layered Architecture

레이어드 아키텍쳐에서의 구성요소(component)는 각 레이어들에 수평적으로 구조화되어있다. 가장 보편적인 레이어드 아키텍쳐는 4개의 레이어로 구조되어있다. presentation layer, business layer, persistence layer , database 이렇게 이루어져 있다.


## 레이어별 역할

- Presentation Layer : UI, 브라우저와 통신 로직을 다룸
- Business Layer :  요청에 따른 비즈니스로직을 다룸
- Persistence Layer : DAO, ORM과 관련된 데이터베이스에 접근하여 저장,조회,수정 등의 로직을 다룸
- Database Layer : 데이터가 저장되는 곳 

## 장점

- 시스템 분석이 용이함 
- 계층간 구조를 나누어 코드 재사용성이 높음
- 변화에 대한 영향력을 제한할 수 있음

## 단점

- 계층을 구분하기 어렵고 잘못 구분할 경우 수정이 빈번할 수 있다.
- 설계 시 계층의 수와 규모를 정하기 어려울 수 있다.