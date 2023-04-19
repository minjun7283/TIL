# @Valid

@Valid는 controller에 전달되는 인자가 유효한 값인지를 확인하는 메소드이다.



# @Validated

@Validated는 AOP기반으로 메소드에 요청이 들어오면 가로채 유효성을 체크한다. @Valid와 다르게 빈 객체라면 어디서든 사용이가능하다.


##### 사용법
```java
@Service
@Validated
public class userService{

    public void join(@Valid LoginDto loginDto)
}
```
