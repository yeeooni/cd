#SQL

> 1986년 ANSI 표준, 1987년 ISO 표준  
데이터베이스 > 액세스 > 표준언어 (구조화 된 쿼리언어 SQL)

* 데이터베이스 생성
  * 테이블 생성(Create)
  * 데이터 검색(Select)
  * 레코드 갱신(Update)
  * 레코드 삽입(Insert)
  * 레코드 삭제(Delete)
* 테이블 수정 (Alter)
* 테이블 삭제 (Drop)

* 관계형데이터베이스(RDBMS) 
  * SQL, MS SQL, SQL Server, IBM DB2, Oracle, MySQL

> 필드 : 테이블의 모든 레코드에 대한 특정 정보를 유지관리하도록 설계된 테이블의 열  
레코드 : 테이블의 가로 엔티티

```sql
-- DB에서 데이터를 선택하는데 사용된다.
-- 테이블의 필드 이름 
SELECT column1, column2,...columnN 
FROM tableName
WHERE '조건문'; 

-- 보드테이블에서 '이름', '주소'를 추출한다.
SELECT 'name', 'address'
FROM 'board';
	

-- 보드테이블의 주소가 '샌프란시스코'인 데이터만 추출한다.
SELECT *
FROM 'board'
WHERE address = '샌프란시스코';

-- 오름차순(ASC), 내림차순(DESC) 정렬 생략 시 Default ASC 
SELECT *
FROM 'board'
ORDER BY email DESC;
```

```sql
-- 데이터 삽입
INSERT INTO(column1, column2, ...columnN)
VALUES(...);

-- 데이터 수정
-- 보드테이블의 회원아이디가 '김' 인 사람의 '모바일'번호를 '6422'로 바꾸어라. 
UPDATE 'board' SET 'mobile' = '6422'
WHERE 'userID' = 'KIM';

-- 데이터 삭제
DELETE
FROM tableName
WHERE  '조건문';
```

> NOT NULL : 열의 NULL값을 허용하지 않는다. (중복성 배제)  
UNIQUE : 열의 모든 값이 서로 다른지 확인한다.(유일한 값으로 존재한다.)  
PRIMARY KEY(NOT NULL + UNIQUE) : 열의 데이터베이스 테이블의 각 레코드를 고유하게 식별한다.  
 
	 

