### [jsp]  Attribute, Scope

- Attribute[속성] : 공유되는 데이터
- Scope[영역] : 속성을 공유할 수 있는 유효 범위 

- Session : 세션이 유지되고 있는 범위안에서, 즉 Session Scope 안에서 서로 다른 페이지 자원이라고 할지라도 객체(데이터)들을 공유할 수 있는 속성을 가지고 있으며 이 속성에 내장된 객체는 **세션이 종료되는 순간**에 반환된다. 한 브라우저 내에 1개의 Session 만 생성된다.
- Request : 클라이언트(사용자)의 요청(Response)이 처리되는 동안에 속성을 사용할 수 있다. 즉, forward(포워딩) 또는 include 방식을 이용하는 경우 여러개의 페이지에서도 요청 정보가 계속 유지되므로 Request 영역의 속성을 여러 페이지에서 공유할 수 있다.

- Application : 웹 애플리케이션이 실행되고 있는 동안 속성을 사용할 수 있다. **가장 큰 영역**이다.

- Page : page 내장 객체가 아닌 pageContext 내장 객체를 통해 접근할 수 있는 영역이다.

  ```jsp
  <title> Attribute Test Form </title>
  <body>
      <h1>
          영역과 속성 테스트 
      </h1>
      
      <form action="#.jsp" method="post">
          <table>
          	<tr>
          		<td colspan="2">Application 영역에 저장될 내용 </td>
          	</tr>
          	<tr>
          		<td>이름</td>
              	<td><input type="text" name="name"/></td>
          	</tr>
          	<tr>
          		<td colspan="2"><input type="submit" value="전송"/></td>
          	</tr>
      	</form>
  	</table>
  </body>
  ```

  #.jsp

  ```jsp
  <%
  	request.setCharacterEncoding("UTF-8");
  	String name = request.getParameter("name");
  	if(name != null && name != undefined && name != ''){
          application.setAttribute("name", name);
      }
  %>
  <!--application 영역에 setAttribute 메소드를 사용하므로 어느 페이지에서 name을 사용할 수 있게 한다. -->
  <title>Attribute Test</title>
  <h1>
      영역과 속성 테스트
  </h1>
  <h3>
      <%=name%> 님 반갑습니다. <br/>
  </h3>
  <form action="##.jsp" method="post">
      <tr>
      	<td colspan="2">Session 영역에 저장할 내용</td>
      </tr>
      <tr>
      	<td>E-MAIL</td>
          <td><input type="text" name="email"/></td>
      </tr>
      <tr>
      	<td>Adress</td>
          <td><input type="text" name="address"/></td>
      </tr>
      <tr>
      	<td>PhoneNumber</td>
          <td><input type="text" name="tel"/></td>
      </tr>
      <tr>
      	<td colspan="2"><input type="submit" value="전송"/></td>
      </tr>
  </form>
  ```

  ##.jsp

  ```jsp
  <%
  	request.setCharacterEncoding("UTF-8");
  	String email = request.getParameter("email");
  	String address = request.getParameter("address");
  	String tel = request.getParameter("tel");
  	
  	if(email != null || address != null || tel != null){
          session.setAttribute("email", email);
  		session.setAttribute("address", address);
  		session.setAttribute("tel", tel);
      }	
  	String name = (String) application.getAttribute("name");
  %>
  <title> Attribute Test </title>
  <h1>
      영역과 속성 테스트
  </h1>
  <h3>
      <%=name%>님의 정보가 저장되었습니다.
</h3>
  <a href="###.jsp">확인하러가기</a>
```
  
  ###.jsp
  
  ```jsp
  <title>Attribute Test</title>
  <h1>
      영역과 속성 테스트
  </h1>
  <table border="1">
      <tr>
          <td colspan="2">Application 영역에 저장된 내용</td>
      </tr>
      <tr>
          <td>이름</td>
          <td><%=applicaton.getAttribute("name")%></td>
      </tr>
  </table>
  
  <table border="1">
      <tr>
      	<td colspan="2">Session 영역에 저장된 내용</td>
      </tr>
      <%
      	Enumeration e = session.getAttributeNames();
      	while(e.hasMoreElements()){
              String attributeName = (String) e.nextElement();// 각 속성들의 이름을 받는다.
              String attributeValues = (String) session.getAttribute(attributeName);
      %>
      	<tr>
      		<td><%=attributeName%></td>
              <td><%=attributeValue%></td>
      	</tr>
      <%
          }
    %>
  </table>
  ```
  
  

