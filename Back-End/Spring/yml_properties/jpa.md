# Jpa properties 설정

- properties 설정에서 jpa와 관련된 설정을 정리해 보았다.


1. spring.jpa.hibernate.ddl.auto

- properties

``` 
spring.jpa.hibernate.ddl.auto = create
```

- yml
```
spring:
    jpa:
        hibernate:
            ddl-auto: create
```

-create :  테이블이 없을경우 생성  
-create-drop : 실행시 table을 생성하고 종료시에 table을 삭제한다.  
-update : 이미 테이블이 존재하며 @Entity가 있는 클래스에 속성이 추가가 되면 기존테이블에 변화없이 Column을 추가한다.  
-validation : application 실행시 @Entity가 붙어있는 클래스와 이미 존재하는 테이블이 정상적으로 매핑되어있는지 확인한다. 만약 제대로 매핑 되어있지 않다면 application을 실행하지 않는다.
-non : 아무것도 하지 않는다.



2. spring.jpa.generate-ddl

- properties
```
spring.jpa.generate-ddl = true
```

- yml
```
spring:
    jpa:
        generate-ddl: true
```

-true 설정할 경우 DDL생성시 데이터베이스 고유의 기능을 사용할수가 있다.


3. spring.jpa.show-sql

-properties
```
spring.jpa.show-sql=true
```

-yml
```
spring:
    jpa:
        show-sql: true
```

-true로 설정하면 jpa를 통해 CRUD를 실행하면 해당 CRUD의 로킹을 보여준다.


4. spring.jpa.database

- properties
```
spring.jpa.database= true
```

- yml
```
spring:
    jpa:
        database: {사용하는 DB}
```

-자신이 사용할 DB를 정의한다.


4. spring.jpa.database.platform

- properties
```
spring.jpa.database.platform= ....
```

- yml
```
spring:
    jpa:
        database-platform: ...
```

- Spring Data Jpa는 기본적으로 hibernate라는 구현체를 사용하는데
hibernate 내부에는 DB에 맞게 SQL문을 생성하는 Dialect가 존재한다.
Dialect는 hibernate가 다양한 데이터베이스를 처리 하기 위해 데이터베이스에 맞는 SQL문을 생성하여 처리할 수 있게 해 준다.



















