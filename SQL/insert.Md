**INSERT**

```sql
INSERT INTO table_name
VALUES(column..);

INSERT INTO member
VALUES ('김의연', 'id', '1234', 31, 'kimiyeon0708', 'nate.com', SYSDATE); 

-- column 정렬
INSERT INTO member(age, id, pass, name, email, email_domain, joindate)
VALUES (23, 'hong', '253', '김의연', 'kimiyeon0708', 'nate.com', SYSDATE);

INSERT INTO member(id, pass, name, joindate)
VALUES ('id', 'java', '김의연', SYSDATE);

INSERT INTO member_detail ( id, tel1, tel2, tel3, address, address_detail, zipcode)
VALUES ('id', '010', '1234', '4567', '서울시 도봉구 쌍문3동', '101호', '08509');


-- Equi Join
SELECT *
FROM member m, member_detail md
WHERE m.id = md.id;

INSERT ALL /* 하나의 INSERT 여러개 column 삽입 */
	INTO member(age, id, pass, name, email, email_domain, joindate)
	VALUES (30, 'oracle', 'a123456789', '오라클', 'oracle', 'oracle.com', SYSDATE)
	INTO member_detail(id, tel1, tel2, tel3, address, address_detail, zipcode)
	VALUES ('oracle', '010', '1234', '5678', '오라클', '연구소', '08509')
SELECT * 
FROM DUAL;	
```
