# Interceptor

## 인터셉터(interceptor)란?

- 요청에 대한 작업중 그 작업을 중간에 가로채가는 존재이다.

- Dispatcher Servlet이 controller에서 들어온 요청을 인터셉터가 끼어들어 요청과 응답을 참조하여 가공할 수 있다.

- 인터셉터는 스프링 컨테이너 안에서 작동한다.

### 인터셉터 사용 예시

1. 세부정인 보안 및 인증 / 인가

2. api 호출 대한 검사

3. controller에게 넘겨주기전 가공
