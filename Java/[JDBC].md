### [JDBC]

_JDBC, 자바 언어로 다양한 종류의 관계형 데이터베이스에 접속하고 SQL문을 수행하여 처리하고자 할 때 사용되는 표준 SQL 인터페이스 API이다. JDBC는 자바의 표준 에디션에서 지원하는 기술로서, 접속하려는 DBMS 서버에 따라서 JDBC 드라이버가 필요하다._

1. JDBC 인터페이스 
   - SE에서 제공하는 java.sql 패키지 
2. JDBC 드라이버
   - java.sql의 인터페이스들을 상속하여 메소드의 몸체를 구현한 클래스 파일들이 필요하다. 
   - 이 파일들을 JDBC드라이버라고 한다.
   - JDBC 프로그램을 위해서는 우선 JDBC 드라이버가 준비되어야한다.
   - WAS가 설치된 HOME 폴더 및 lib 폴더, 각 웹 애플리케이션 /WEB-INF/lib 폴더에 저장

3. JDBC 드라이버 로딩

```java
Class.forName("oracle.jdbc.driver.OracleDriver");
```



4. DBMS 서버 접속

   - JDBC 드라이버의 사용준비가 완료되면, 첫 번째 DB작업으로 DB서버와의 연결작업
   - Java.sql 패키지의 DriverManager 클래스의 getConnection() 메소드를 이용

   ```java
   Connection conn = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:xe", "id", "passWord");
   ```

   - String url : 접속할 서버의 URL, 프로토콜, 서버 주소, 서버 포트, DB이름 
   - String user : DB서버에 로그인할 계정
   - String passWord : DB서버에 로그인할 비밀번호



5. Statement 

   - Connection을 자바 프로그램과 DB사이에 연결이 되었다면, 이 연결을 통해 자바 프로그램은 DB 쪽으로 SQL문을 전송하고, DB는 처리된 결과를 다시 자바 프로그램으로 전달한다. 그 역할을 하는 객체가 Statement.

   ```java
   Statement stmt = conn.createStatement();
   ```



6. ResultSet

```java
void afterLast() //커서를 끝 빈 행으로 위치
void beforeFirst() //커서를 시작 빈행으로 위치시키는 메소드
boolean next() //커서 다음에 레코드가 있는지 판단, 없으면 false, 있으면 true
```



7. 자원 해제

``` java
rs.close();
stmt.close();
conn.close();
```

