# WebSocket

WebSocket은 HTTP 프로토콜과 호환되며 양방향 통신을 제공하기 위한 프로토콜이다.

## 사용이유

![image](https://github.com/minjun7283/TIL/assets/107666764/d9c20e84-99f9-42fa-add4-e1e28c543539)

                    출처 : wldus9503님 블로그

기존 HTTP 프로토콜은 클라이언트가 요청을 보내고, 웹서버가 응답하는 방식이었며 서버는 응답을 보내면 웹 브라우즈와의 연결을 끊는다. 하지만 웹 소켓은 클라이언트가 먼저 요청을 보내지 않아도 서버가 먼저 데이터를 보낼 수 있다.


접속할 떄까지는 HTTP 프로토콜을 사용하며 그 이후에는 자체 WebSocket 프로토콜로 통신한다.


WebSocket이 존재하기 전에는 Polling, Long Polling, Streaming 등으로 해결해 왔었다.

## Polling

![image](https://github.com/minjun7283/TIL/assets/107666764/e65508c2-858a-4060-8265-2d87bd7b3595)

    출러 : https://rubberduck-debug.tistory.com/123

클라이언트가 평범하게 HTTP Request를 계속해서 요청을 보내 이벤트 내용을 전달받는 방식이다.가장 쉬운 방법이지만 클라이언트가 계속 요청을 보내야 하기떄문에 클라이언트의 수가 많아지면 서버의 부담이 커진다. HTTP Request Connection을 계속 맺고 끊는 방식 자체가 매우 부담이 되고, 실시간 정도의 빠른 응답을 기대하기 어렵다.

## Long Polling

![image](https://github.com/minjun7283/TIL/assets/107666764/fb115d4a-389c-4cf5-a565-6a805cad5091)

    출처 : https://rubberduck-debug.tistory.com/123

클라이언트에서 서버로 HTTP Request 요청을 보낸다. 서버는 대기하다 클라이언트에 보내야할 이벤트가 생기면 Response를 반환하고 연결이 종류된다. 곧이어 다시 클라이언트가 서버로 HTTP Request 요청을 보내놓고 다시 이벤트가 생길 때까지 대기하는 방식이다. Polling 보나는 서버의 부담이 적으나 이벤트가 자주 발생할 경우 Polling 방식과 별 차이가 없으며 다수의 클라이언트에 이벤트가 발생하면 서버의 부담이 급증한다. 

## Streaming

![image](https://github.com/minjun7283/TIL/assets/107666764/500d00e7-adf3-46a6-9355-565e4d187a4a)

    출처 : https://rubberduck-debug.tistory.com/123

Long Polling과 똑같이 먼저 클라이언트가 서버에 요청을 보낸다. 그 후 서버는 클라이언트 메세지를 반환하고 연결을 끊지 않고 필요한 메세지만 보내기를 반복하는 방식이다. Long Polling과 비교하여 다시 HTTP Request Connection을 다시 하지 않아도 되어 부담이 좀 더 적다.

## WebSocket 설명

![image](https://github.com/minjun7283/TIL/assets/107666764/107a5d1c-484a-45ec-9ab3-13bdb70ea87f)

    출처: https://yuricoding.tistory.com/134

HTTP의 [연결 -> 연결끊기]의 방식이 효율이 많이 떨어지고 웹 브라우즈말고도 외부의 플러그인이 항상 필요하게 되는 상황을 극복하기 위해 2014년 HTML5 에 웹소켓을 포함하였다고 한다. 프로토콜 요청은 [ws://~]로 시작한다.


