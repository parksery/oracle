-- * 은 모든 열 모든 데이터를 조회
SELECT *
FROM employees; -- 명령어는 대문자로 사용을 권장(필수는 아님);

-- 원하는 열들의 이름만 선택해서
--employee_id를 기준으로 내림차순 정렬 후 열어보기
SELECT  employee_id, first_name, last_name
FROM employees
ORDER BY employee_id DESC, first_name ASC;--DESC 내림차순
--select 뒤의 열들만 조회


-- 특정 열만 출력
SELECT job_id
FROM employees;


--별명사용
SELECT employee_id AS 사원번호, first_name AS 이름, last_name AS 성
FROM employees;
