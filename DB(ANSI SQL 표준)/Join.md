(코드 제외) 내용 출처 : https://tragramming.tistory.com/74

# Inner Join

* 각 테이블에서 조인 조건에 일치되는 데이터만 가져온다.

* 교집합을 생각하면 됨.

* ```sql
  --hr 스크립트
  SELECT * FROM employees e

      INNER JOIN
      departments d
      ON e.department_id = d.department_id;
  ```
---
<br></br>

# Outer Join

* 조건에 일치하는 데이터, 일치하지 않는 데이터 **모두** SELECT 함.

* 성능저하(TABLE ACCESS FULL)을 야기시키므로 최대한 사용 자제

* TABLE ACCESS FULL : 테이블을 처음부터 끝까지 읽어서 찾는 것을 뜻함.

* 어떤 테이블이 중심이 되느냐에 따라 세분화 됨.
> 1. Left Outer Join
> 2. Right Outer Join
> 3. Full Outer Join

<br></br>

### Left Outer Join
---
* ```sql
  --hr 스크립트
  SELECT
      e.first_name 이름, d.department_name 부서명 FROM employees e --TABLE_A
      
      LEFT OUTER JOIN
      departments d --TABLE B
      ON e.manager_id = d.manager_id;
  ```
* Left Outer Join을 기준으로 TABLE_A은 왼쪽에, TABLE_B는 오른쪽에 언급됨.
  
* TABLE_A가 주(主) 테이블, TABLE_B가 종(從)테이블이 됨.
<br></br>

### Right Outer Join
---
* 오른쪽 테이블이 기준이 됨.
  
* 조인 조건에 부합하는 데이터가 조인 당하는 테이블(왼쪽)에 있으면 해당 데이터를, 부재하면 NULL로 SELECT 됨.
  
* ```sql
  --hr 스크립트
  SELECT
    e.first_name 이름, d.department_name 부서명  FROM  employees e
      
    RIGHT JOIN
    departments d
    ON d.department_id = e.department_id;
  ```
<br></br>

### Full Outer Join
---
* 양쪽 테이블 모두가 기준이 됨.

* 조인 조건에 부합하는 데이터가 조인 당하는 테이블(왼쪽 OR 오른쪽)에 있으면 해당 데이터를, 부재하면 NULL로 SELECT 됨.

* ```sql
  --hr 스크립트
  SELECT *
       FROM employees e

       FULL OUTER JOIN
       departments d
       ON d.department_id = e.department_id;
  ```
<br></br>

### Self Join
---
* 테이블이 자기 자신을 마치 다른 테이블처럼 취급하여 조인함.

* Main 및 Sub 테이블과 컬럼이 모두 같기 때문에, 특정 열을 명시할 때 열이 모호하다는 오류가 발생할 수 있다. 이런 점에서 반드시 **알리아스(ALIAS)를 사용하여 조인**하는 것을 권고한다.

* ```sql
  --hr 스크립트
  SELECT e.employee_id  사번, e.first_name 이름, m.first_name 매니저_이름
       FROM employees e -- alias 사용하기!

       JOIN
       employees m 
       ON e.manager_id = m.employee_id; --e(사원).manager_id 가 m.employee_id 와 같다면 해당 employee_id를 가진 사람이 manager 임.
  ```
<br></br>

### Non-Euqi Join
---
* ANSI의 Non-Euqi Join은 오라클의 Non-Euqi Join와 같다.

* ```sql
  --ex)
  SELECT *
    from table1
    join
    table2
    on column_name between 조건1 and 조건2
  ```

* ```sql
  --hr스크립트
  --직원의 급여가 몇 등급인지 조회하시오.(출력은 이름, 급여, 등급)
  --(단, 급여가 많은 순부터, 같은 급여면 이름 오름차순부터!)
  SELECT
    e.first_name 이름, e.salary 급여, s.grade 등급 FROM employees e
    JOIN salgrade s
    ON e.salary BETWEEN s.lsal and s.hsal
    ORDER BY e.salary DESC, e.first_name;
  ```