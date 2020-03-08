JOIN

- INNER JOIN

- OUTER JOIN

  - 동일한 값이 없는 행도 반환할 때 사용
  - 즉, A,B 테이블을 JOIN할 경우, 조건에 맞지 않는 데이터도 표시하고 싶을 때
  - LEFT/RIGHT OUTER JOIN 기준이 되는 테이블은 **드라이빙 테이블**
  - LEFT OUTER JOIN
    ![leftouterjoin](/home/kimeuiyeon/cd/img/sql-left-join.png "LEFET OUTER JOIN")
    - 조인 수행 시 먼저 표기된 좌측 테이블에 해당하는 데이터를 먼저 읽는다.
    - 왼쪽 테이블이 기준이 된다. 오른쪽 테이블에 있는 값이 왼쪽 테이블과 같은 값이 없는 경우 오른쪽 테이블에서 가져오는 컬럼들을 왼쪽테이블에서 NULL로 채운다. OUTER를 생략할 수 있다.
    - 즉, 왼쪽 테이블의 무조건 결과값에 포함되어 나온다.

  

  - RIGHT OUTER JOIN
    ![rightouterjoin](/home/kimeuiyeon/cd/img/sql-right-join.png)
    - 우측 테이블이 기준이 된다.
    - 우측 테이블의 값은 무조건 포함되어 나온다.