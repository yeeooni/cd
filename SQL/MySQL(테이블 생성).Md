```sql
-- 'board'
CREATE TABLE IF NOT EXISTS 'board'(
	'useId' VARCHAR(10) COLLATE UTF8_bin NOT NULL, 
	'name' VARCHAR(10) COLLATE UTF8_bin NOT NULL,
	'address' VARCHAR(30) COLLATE UTF8_bin NOT NULL,
	'mobile' VARCHAR(10) COLLATE UTF8_bin NOT NULL,
	'email' VARCHAR(10) COLLATE UTF8_bin NOT NULL,
	'mDate' DATE NOT NULL
) ENGINE = MYISAM DEFAULT CHARSET = UTF8 COLLATE = UTF8_bin;
```

* MYISAM이 유리한 경우
  * SELECT 위주의 작업만 필요한 경우
  * 전문 검색이 필요한 경우
  * 트랜잭션이나 복구등이 필요없을 경우
  * 한 번에 대량의 데이터를 입력하는 배치성 테이블 
