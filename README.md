-- * 은 모든 열 모든 데이터를 조회
SELECT *
FROM employees; -- 명령어는 대문자로 사용을 권장(필수는 아님);

-- 원하는 열들의 이름만 선택해서
--employee_id를 기준으로 내림차순 정렬 후 열어보기
SELECT  employee_id, first_name, last_name
FROM employees
ORDER BY employee_id DESC, first_name ASC;--employee_is를 기준으로 DESC 내림차순정렬
--select 뒤의 열들만 조회


SELECT DISTINCT job_id
FROM employees;
--job_id를 기준으로 고유한 값들만 즉, 중복 제거된 결과



--별명사용
SELECT employee_id AS 사원번호, first_name AS 이름, last_name AS 성
FROM employees;
--AS를 사용하여 열이름을 변경하여 출력한다



SELECT employee_id, first_name||last_name
FROM employees;
--두개열을 붙여서 하나의 데이터 값으로 나타낸다

SELECT employee_id, first_name|| ' ' ||last_name
,email||'@'||'company.com'
FROM employees;
--두개열을 붙여서 하나의 데이터 값으로 나타낸다
--가운데 한칸 띄기

SELECT employee_id, salary, salary+500, salary-100, (salary*1.1)/2
FROM employees;
--새로운 열을 생성하는 것이 아니라 보여만 주는 것이다

SELECT employee_id AS 사원 번호, 
salary AS 급여,
salary+500 AS 추가급여, 
salary-100 AS 인하급여
, (salary*1.1)/2 AS 조정 급여
FROM employees;
--열이름을 별명으로 잠시 보여줄때만 사용된다

SELECT *
FROM employees
WHERE employee_id = 100;

--아이디가 100인 애들만 출력




SELECT *
FROM employees
WHERE first_name = 'David';

--first_name 에서 David만 출력


SELECT *
FROM employees
WHERE salary BETWEEN 10000 AND 20000;
-- BETWEEN a AND b 사이의 수 >=   <=

SELECT *
FROM employees
WHERE salary IN(1000,17000,24000);
-- IN =와 유사하지만 =은 하나만 조건으로 지정하고 
--IN은 값을 여러개 설정


SELECT *
FROM employees
WHERE job_id LIKE 'AD%';

-- LIKE는 명확하지 않은 조건으로 찾을 때
-- ~처럼 ~같은 
-- 조건에는 문자나 숫자를 포함할 수 있다
--% 모든 문자 _한글자 라는 의미이다.

SELECT *
FROM employees
WHERE salary > 4000
AND job_id = 'IT_PROG'
OR job_id = 'FI_ACCOUNT';
--조건을 모두 충족하는 데이터를 검색
--AND나 OR를 계속 붙여 추가할 수 있다

SELECT *
FROM employees
WHERE employee_id <> 105;
--<>아니다. !=

SELECT *
FROM employees
WHERE manager_id IS NOT NULL;
-- IS NULL <> IS NOT NULL
