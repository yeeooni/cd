**FUNCTION**

```sql
 
/* ROUND(DATA, 1) : 소수부 둘째자리에서 반올림
   ROUND(DATA, -1) : 정수부 첫째자리에서 반올림 */

SELECT 1234.5438, ROUND(1234.5438, 0), ROUND(1234.5438, 1), ROUND(1234.5438, -1), ROUND(1234.5438, 3), ROUND(1234.5438, -3)
FROM dual;

/* TRUNC(DATA, 1) : 소수부 둘째자리부터 버림
   TRUNC(DATA, -1) : 정수부 첫째자리부터 버림 */

SELECT 1234.5438, TRUNC(1234.5438, 0), TRUNC(1234.5438, 1), TRUNC(1234.5438, -1), TRUNC(1234.5438, 3), TRUNC(1234.5438, -3)
FROM dual; 

/*FLOOR 소수점 이하 제거 */

SELECT  FLOOR(1234.5438)
FROM dual;

/* MOD 나머지 연산 */

SELECT mod(5, 3)
FROM dual;

/* ABS 절대값 */

SELECT abs(-5)
FROM dual;

/* 사번, 이름 급여, 커미션 포함 급여( 100의 자리수로 반올림) */

SELECT employee_id, first_name, salary, commission_pct * salary + salary, ROUND(commission_pct * salary + salary, -2) 
FROM employees
WHERE commission_pct IS NOT NULL;

```
