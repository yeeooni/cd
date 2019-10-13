**CREATE**

```sql
CREATE TABLE table_name(
	column dataType
	CONSTRAINTS table_column_pk PRIMARY KEY (column)
);

CREATE TABLE table_name2(
	column dataType
	CONSTRAINTS table_column_fr FOREIGN KEY (column) REFERENCES table_name (cloumn)
);
```
###### 회원테이블

|논리이름|물리이름|데이터타입|
|:-------|:-------|:--------:|
|이름|name|varchar2(30)|
|아이디|id|varchar2(16)|
|비밀번호|password|varchar(16)|
|나이|age|number(3)|
|이메일|email|varchar2(30)|
|이메일도메인|email_domain|varchar2(30)|
|가입일|joindate|date|

###### 회원상세테이블

|논리이름|물리이름|데이터타입|
|:-------|:-------|:--------:|
|아이디|id|varchar2(16)|
|우편번호|zipcode|varchar(5)|
|일반주소|address|varchar2(100)|
|상세주소|address_detail|varchar2(100)|
|전화번호1|tel1|varchar(3)|
|전화번호2|tel2|varchar(4)|
|전화번호3|tel3|varchar(4)|

```sql

CREATE TABLE member( /* 멤버 테이블 */
	name varchar2(30) NOT NULL, /* 이름 */
	id varchar2(16), /* 아이디 */
	pass varchar2(16) NOT NULL, /* 패스워드 */
	age number(3) CHECK (age < 150), /* 나이 */
	email varchar2(30), /* 이메일 */
	email_domain varchar2(30), /* 이메일 도메인 */
	joindate date DEFAULT SYSDATE, /* 가입일 */
	CONSTRAINTS member_id_pk PRIMARY KEY (id)
);

CREATE TABLE member_detail( /* 멤버 상태 테이블 */
	id varchar2(30), /* 아이디 */
	zipcode varchar(5), /* 우편번호 */
	address varchar2(100), /* 주소 */
	address_detail varchar2(100), /* 상세 주소 */
	tel1 varchar(3), /* 전화번호 첫번째자리 */
	tel2 varchar(4), /* 두번째 자리 */
	tel3 varchar(4) /* 세번째 자리 */
	CONSTRAINTS member_detail_id_fk FOREIGN KEY (id) REFERENCES member (id)
);

-- 테이블 구조만 출력할 때
CREATE TABLE table_name 
AS
SELECT *
FROM member
WHERE 1=0;

```



