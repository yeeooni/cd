# WEB SERVER & WAS

1. Web Server (웹 서버)
_웹 브라우저(IE, Chrome, Firefox) 클라이언트로부터 HTTP 요청을 받아 HTML, Image, file 등을 제공해주는 Server_  
_즉 사용자가 요청을 보내면 그 명령에 대한 처리를 실행하고 다시 사용자에게 응답을 해주는 역할을 수행한다._  
_자주 사용되는 웹 서버는 Apache, IIS, 웹 투비 등이 있다._  
_동적 컨텐츠가 들어올 경우 WAS Server로 데이터를 넘겨준다._

2. WAS(Web Application Server)
_웹 어플리케이션 서버, 웹 응용 서버라고 불리고 HTTP를 통해 사용자 컴퓨터나 장치에 어플리케이션을 수행해 주는 미들웨어_  
_tomcat, 제우스, 웹스피어, 젬스톤_  
_Apache, tomcat을 연동하여 사용하는 이유는 로드 밸런싱이 가능하고 부하를 분산하기 위해 사용_  
