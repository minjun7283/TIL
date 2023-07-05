# oauth


## oauth란?

구글, 트위터, 네이버와 같은 다양한 플랫폼의 사용자 데이터에 접근하기 위한 사용자의 접근 권한을 위임 받을 수 있는 표준 프로토콜이다.

oauth2를 사용하기 위해서는 자신이 사용하는 플랫폼에 사용신청을 해야한다. 플랫폼마다 조금씩 다른 부분이 있지만 공통점은 Redirect Url을 설정해줘야한다는 것이다.

## Redirect Url이란?

oauth2 서비스는 인증에 성공한 사용자를 Redirect Url로 보내준다. 위에서 플랫폼에 사용신청으로 등록한 url을 설정하는 이유는 승인되지 않는 url로 인증 코드(Authorization code)가 탈취당할 가능성을 배제하기 위해서이다. 
또한 Redirect Url은 https만 허용하지만 locaolhost는 예외로 처리된다.