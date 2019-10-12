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
WHERE salary BETWEEN 5000 AND 12000; /* 급여 5000이상 12000 이하 사번, 이름, 급여, 부서번호 */



```
