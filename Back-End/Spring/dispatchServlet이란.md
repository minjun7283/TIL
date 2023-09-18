# dispatcher Servlet이란?

#### HTTP 프로토콜로 들어오는 요청을 가장 먼저 받아 컨트롤러에 위임하는 프론트 컨트롤러이다.


## dispatcher Servlet의 장점
 
    과거에는 모든 서블릿을 URL 매핑을 위해 web.xml에 모두 등록시켜주었지만, dispacth Servlet이 해당 애플리케이션에서 오는 모든 요청을 핸들링해주고 공동작업을 처리하면서 상당히 편리해졌다. Controller만 구현해주면 dispatch Servlet이 알아서 적합한 Controller에 위임해준다.

## 정적 자원 처리 
    dispatcher Servlet이 요청을 Controller에 위임하는 방식은 효율적이나, 모든 요청을 처리하다보니 이미지나 HTML/CSS/JavaScript와 같은 정적 파일마저 모두 가로채 정적 자원을 불러오지 못하는 일이 발생하였다. 이러한 문제로 인하여 다음과 같은 방안 등이 마련되었다.
    
1. 정적 자원 요청과 애플리케이션 요청을 분리한다.

2. 애플리케이션 요청을 탐색하고 없으면 정적 자원을 처리한다.


# dispatch Servlet의 동작 원리
![image](https://github.com/minjun7283/TIL/assets/107666764/a78e7360-40de-49b1-bcd3-602cf8cf5743)

1. 클라이언트로부터 요청이 들어오면 dispatcher Servlet이 받음
2. 요청정보에 따라 위임할 Controller를 Handler Mapping이 탐색한다.
3. dispatch Servlet이 handler Adapter를 사용하여 Controller에 위임한다.
4. 이후 Contorller는 service를 호출하여 로직을 처리한다.
5. 비지니스 로직을 처리한 후 값을 반환한다. 응답 데이터를 반환할 경우 주로 ResponseEntity를 반환한다.
6. 반환된 값을 handler Adapter가 값에 따라 처리하여 dispatch Servlet으로 반환한다.
7. 이렇게 반환된 값을 dispatch Servlet이 클라이언트에 여러 필터에 거쳐 반환한다. 




