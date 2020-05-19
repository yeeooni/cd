<center>[JSP] Servlet</center>

1. Servlet (서블릿)
   - 웹 프로그래밍에서 클라이언트의 요청을 처리, 결과를 클라이언트에게 전송	
     - 예) 사용자가 로그인 시 아이디, 비밀번호를 입력하고 로그인 액션.
     - 서버는 클라이언트의 아이디, 비밀번호를 확인 다음 페이지를 노출.
2. 특징
   - 클라이언트의 요청에 대해 동적으로 작동하는 웹 어플리케이션 컴포넌트
   - html 사용, 요청 응답
   - java thread 이용 동작
   - MVC 패턴 Cottroller로 이용
   - HTTP 프로토콜 서비스를 지원하는 javax.servlet.http.HttpServlet 상속
   - html 변경 시 Servlet 재 컴파일
3. 동작 순서
   - 클라이언트 -> HTTP Request를 Servlet Container로 전송
   - HTTP Request를 전송받은 Sertvlet Container HttpServletRequest, HttpServletResponse 객체 생성
   - web.xml 클라이언트가 전송한 url 분석
   - service 메소드 호출 -> post, get 여부 확인 후 doGet(), doPost() 호출
   - 응답이 끝나면 HttpServletRequest, HttpServletResponse 소멸

---

### [JSP] Java Server Page

- java 코드가 존재하는 html 