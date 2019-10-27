# Spring
- POJO ( Plain Old Java Object ) 방식의 프레임워크 특정 라이브러리를 사용할 필요가 없어 개발이 쉽다.
- 관점지향프로그래밍 ( Aspect Oriented Programming ) 지원. 트랜잭션, 로깅, 보안 등 실제 비지니스 로직과 분리할 수 있도록 지원.
- 의존성 주입 ( Dependency Injection ) 지원. 어떤 객체가 필요하는 객체를 자기 자신이 직접 생성하는 것이 아니라, 외부에 있는 곳에서 자신이 필요로 하는 객체를 받는 것.
- 제어 반전 ( Inversion Of Controller ) 지원.  
컨트롤의 제어권이 개발자가 아니라 프레임워크에 있다.

**Maven Dependencies**

**pom.xml**
- 라이브러리 관리
- <dependency>하나의 라이브러리</dependency> 
- <repositories>실제 라이브러리를 다운받을 저장소</repositories>

**Controller.java**
- 웹 클라이언트에서 들어온 요청을 해당 비지니스 로직으로 분기  
수행결과를 응답 해주는 Dispatcher 역할을 담당하는 클래스  
- @RequestMapping 웹 클라이언트에서 들어온 요청에 해당하는 비지니스 로직을 찾아주는 역할

**Servlet-context.xml**
- 서블릿 관련 설정 파일
- <beans:property name="prefix" value="/WEB-INF/views/"/> 전체경로
- <beans:property name="subfix" value=".jsp"/> 파일확장명

**서블릿 설정 변경**
- 서블릿은 자바에서 동적 웹 프로젝트를 개발할 때, 사용자의 요청과 응답을 처리해주는 역할.


