**SELECT**

```sql
SELECT column_name /* 3 */
FROM table_name /* 1 */
WHERE conditions /* 2 */
GROUP BY
HAVING
ORDER BY /* 4 */

SELECT employee_id, first_name, salary, department_id
FROM employees
WHERE salary >= 5000; /* 급여 5000 이상 사번, 이름, 급여, 부서번호 */

SELECT first_name, department_id
FROM employees 
WHERE employee_id = '100'; /* 100번 사번 이름, 부서번호 */

SELECT location_id, postal_code
FROM locations
WHERE city = upper('seattle'); /* seattle 도시 지역번호, 우편번호 */

SELECT employee_id, first_name, salary, department_id
FROM employees 
WHERE salary >= 5000 AND salary <= 12000;

SELECT employee_id, first_name, salary, department_id
FROM employees
WHERE salary BETWEEN 5000 AND 12000; /* 급여 5000이상 12000 이하 사번, 이름, 급여, 부서번호 */

SELECT employee_id, first_name, salary, department_id
FROM employees
WHERE salary > 5000 AND salary < 12000; /* 급여 5000초과 12000미만 사번, 이름, 급여, 부서번호 */

-- BETWEEN A AND B 

SELECT employee_id, first_name, salary, department_id
FROM employees
WHERE salary NOT BETWEEN 5000 AND 12000

SELECT employee_id, first_name, department_id
FROM employees
WHERE department_id = 50 OR department_id = 60 OR department_id = 80;

-- IN

SELECT employee_id, first_name, department_id
FROM employees
WHERE department_id IN (50, 60, 80); /* 부서번호 50, 60, 80인 사번, 이름, 부서번호 */

SELECT employee_id, first_name, department_id 
FROM employees
WHERE department_id != 50 AND department_id != 60 AND department_id != 80;

-- NOT IN

SELECT employee_id, first_name, department_id
FROM employees
WHERE department_id NOT IN (50, 60, 80); /* 부서번호 50, 60, 80 모두 아닌 사번, 이름 부서번호 */

-- ANY 등가비교를 할 때 하나라도 조건이 만족하면된다.
 
SELECT employee_id, first_name, salary
FROM employees
WHERE salary >= 3000 OR salary >= 8000 OR salary >= 5000;

SELECT employee_id, first_name, salary
FROM employees
WHERE salary >= ANY(3000, 8000, 5000);

-- ALL 등가비교를 할 때 모든 조건이 만족해야한다.

SELECT employee_id, first_name, salary
FROM employees
WHERE salary >= 3000 AND salary >= 8000 AND salary >= 5000;

SELECT employee_id, first_name, salary
FROM employees
WHERE salary >= ALL(3000, 8000, 5000);

SELECT employee_id 
FROM employees
WHERE first_name = 'Steven'; /* 이름 Steven 사번 */

SELECT employee_id, first_name
FROM employees
WHERE first_name LIKE '%e%'; /* 이름 'e'를 포함하고 있는 사원 사번, 이름 */

SELECT employee_id, first_name
FROM employees
WHERE first_name LIKE '%y'; /* 이름 'y'로 끝나는 사번, 이름 */

SELECT employee_id, first_name
FROM employees
WHERE first_name LIKE '%e___'; * 이름 끝에서 세번째 'e' 사번, 이름 *?

SELECT employee_id, first_name, department_id
FROM employees
WHERE department_id ^= 50; /* 부서번호 50이 아닌 사번, 이름 부서번호 */

SELECT employee_id, fisrt_name, salary
FROM employees
ORDER BY salary DESC; /* 급여순 내림차순 정렬 */

-- 별칭 정렬 가능 

SELECT department_id did, employee_id eid, first_name, salary sal
FROM employees
ORDER BY did, sal DESC;

-- 중복행 제거 

SELECT [all | DISTINCT ] ( * | col1, col2, col3, conl^n) 
FROM table_name 

--SUB QUERY

SELECT employee_id, first_name, department_id /* 도시 seattle 사번, 이름, 부서번호 */
FROM employees
WHERE department_id IN ( SELECT department_id
			 FROM departments
			 WHERE location_id = ( SELECT location_id
					       FROM locations
					       WHERE lower(city) = lower('seattle')));
-- NVL : coloumn에 NULL이 존재한다면.

SELECT NVL(column, 0)
FROM table_name; /* NULL >> 0 */

-- 별칭 ( Alias )

SELECT employee_id AS 사번, first_name AS 이름, salary AS 급여
FROM employees;

SELECT employee_id 사번, first_name 이름, salary 급여
FROM employees;

SELECT employee_id "사번", first_name "이름", salary "급여"
FROM employees;

-- 연결자 column1 || '문자열 OR 공백' || column2

SELECT '사번이 ' || employee_id ||'인 사원의 이름은 ' || first_name ||' '|| last_name || '입니다.
FROM employees;
```
