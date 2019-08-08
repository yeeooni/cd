![TABLE CREATE](../img/PostgreSQL(CREATE).png "PostgreSQL")

1. Ubuntu PostgreSQL 설치.
- `sudo apt-get update` 패키지 업데이트 
- `sudo -s` `aptitud show postgresql | grep State` 기존 설치 확인
- `apt-get install postgresql` 설치
- `dpkg -l | grep postgres` 패키지 설치 확인
- `cat /etc/passwd | grep postgres` 관리자 계정 생성 확인
- `/etc/init.d/postgresql status` `netstat -tnlp | grep postgres` localhost에서만 접속 가능
- `sudo -u postgres psql template1` postgres 계정 패스워드 변경
- `sudo -i -u postgres` postgres 계정으로 접속
- `psql` 데이터베이스 접속
- `\q` 나가기
- `\d` 데이터베이스 전체 확인 `\dt` 테이블만 확인
