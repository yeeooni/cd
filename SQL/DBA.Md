# 오라클 DB 계정 생성 및 사용자 확인 
> 오라클의 관리자 계정은 DBA 권한을 가지고 있어야 한다.


```sql
-- 현재 생성된 계정 확인
SELECT *
FROM dba_users;

SELECT *
FROM all_users;

-- 사용자에게 부여된 시스템 권한 확인
SELECT *
FROM dba_sys_privx
WHERE GRANTEE = '사용자명';

-- 사용자에게 부여된 롤 확인
SELECT *
FROM dba_role_privs
WHERE GRANTEE = '사용자명';


-- 사용자에게 부여된 롤에 부여된 시스템 권한 확인 
SELECT *
FROM dba_sys_privs
WHERE GRANTEE = '롤명';

-- 사용자가 소유한 모든 테이블 확인
SELECT 테이블명
FROM user_tables;

-- 계정 비밀번호 변경
ALTER USER 계정명 
IDENTIFIED BY 변경할 비밀번호; 

-- 계정 권한 할당
GRANT 권한명 TO 계정;
```

|시스템 권한 종류| 내용 |
|:--:|:--:|
|CREATE USER|데이터 베이스 유저 생성 권한|
|SELECT ANY TABLE|모든 유저의 테이블 조회 권한|



