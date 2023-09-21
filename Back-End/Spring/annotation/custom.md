# Custom Annotation

다른 사람들에 github들을 찾아보다보니 커스텀 어노테이션이라는게 있어 한번 알아보고 정리해 보왔다.

## Annotatopn이란?

어노테이션이란 소스코드에 포함되는 메타데이터이다. 앱이 처리하는 데이터가 아닌 컴파일 과정, 실행과정에서 코드가 어떻게 처리해야하는지 알려주는 용도이다.


## Custom Annotation 선언

### java

```java
public @interface custom{

}
```

### kotlin
```kotlin
annotation class custom{

}
```

## meta Annotation

meta Annotation은 다른 어노테이션에 적용하기 위한 어노테이션이다. 


### 종류

1. Retention : 해당 어노테이션이 언제까지 적용되는 범위를 설정한다.
    - Retention.SOURCE : 컴파일전까지만 유효하고 컴파일 이후에는 사라진다.
    - Retention.CLASS : 컴파일러가 클래스를 참조할때까지 유효하다.
    - Retention.RUNTIME : Reflection을 사용하여 jvm에 의해 계속 참조가 가능하다.

2. Documented : JavaDoc 생성 시 Document에 포함되도록 함
3. Target : annotation이 어디에 적용될지 결정하기 위해 사용합니다.
    - AnnotationTarget.CLASS : 클래스에 적용
    - AnnotationTarget.ANNOTATAION_CLASS : 어노테이션 클래스에 적용
    - AnnotationTarget.FUNCTION : 함수에 적용
    - AnnotationTarget.TYPE_PARAMETER : Generic에서 쓰이는 파라미터에 적용
    - AnnotationTarget.LOCAL_VARIABLE : 지역 변수에 적용
    - AnnotationTarget.FIELD : 	kotlin property 를 뒷받침하는 backing field에 적용
    - AnnotationTarget.VALUE_PARAMETER : 생성자 파라미터 혹은 함수 파라미터에 적용
    - AnnotationTarget.CONSTRUCT : 생성자에 적용
    - AnnotationTarget.PROPERTY : kotlin property에 적용
    - AnnotationTarget.PROPERTY_GETTER : kotlin property getter에 적용
    - AnnotationTarget.PROPERTY_SETTER : kotlin property setter에 적용
    - AnnotationTarget.TYPE : 타입에 적용
    - AnnotationTarget.TYPE_ALIAS : type alias에 적용
    - AnnotationTarget.FILE : 파일에 적용
    - AnnotationTarget.EXPRESSION : 표현식에 적용(ex : if else문)

    kotlin 언어로 사용시 위와 같은 형태로 선언하면 되지만 java는 조금 다를 수 있다.
4. Inherited : 해당 어노테이션을 하위 클래스에 적용한다.
5. Repeatable : java8부터 지원되며, 연속적으로 어노테이션을 선언하는 것을 허용한다.




    