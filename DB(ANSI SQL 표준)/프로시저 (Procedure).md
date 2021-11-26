# 프로시저 (Procedure)

* 용도

1. 어떠한 동작을 절차적 일괄처리 작업하는데 사용
2. SQL Server에서 사용하는 프로그래밍 기능

* 특징

1. SQL Server의 성능 향상(첫 실행시 컴파일, 재컴파일 안함)
2. 네트워크 전송량 감소(긴 쿼리문장의 단순화)

---
<br></br>

## 기본문법

1. (인수없는)프로시저 생성방법

* ```sql
    CREATE OR REPLACE PROCEDURE 프로시저이름 

    IS

    [

    변수이름 데이터타입;  -- 프로시저내에서 사용할 변수선언

    변수이름 데이터타입;

    변수이름 데이터타입;

    ..

    ]

    BEGIN

    기능 구현;

    END;

  ```

* ```sql
    --ex)
    SET SERVEROUTPUT ON; --dbms_output에 의한 PL/SQL의 표준출력 담당.

    CREATE OR REPLACE PROCEDURE p_test 
    IS 
        I_MESSAGE VARCHAR2(100) := 'http://goddaehee.tistory.com'; 

    BEGIN 
        dbms_output.put_line(I_MESSAGE); --http://goddaehee.tistory.com 호출됨
    END; 
    EXEC p_test; --프로시저 호출
  ```

---

2. (인수있는)프로시저 생성방법

* ```sql
    CREATE OR REPLACE PROCEDURE 프로시저이름(

    변수이름 IN 데이터타입, 변수이름 IN 데이터타입, .... --IN 생략가능

    )

    IS

    [

    변수이름 데이터타입;  -- 프로시저내에서 사용할 변수선언

    ..

    ]

    BEGIN

    기능 구현;

    END;
  ```

* ```sql
    --ex)
    CREATE OR REPLACE PROCEDURE p2_test( p_name IN VARCHAR2 ) 
    IS 
    BEGIN 
        dbms_output.put_line(p_name||' 님 안녕하세요?'); 
    END; 
    EXEC p2_test; --프로시저 호출 (오류발생 ) 
                  -- (프로시저에 in이 있으면서 기본값이 없기 때문에 반드시 인수값 필요함) 
    EXEC p2_test('goddaehee');
  ```

---
<br></br>

## 인수의 타입 선언 정리

1. IN -> 내부 프로그램에 제공
   
   * 변수이름 IN VARCHAR2;  --인수선언할때 byte수 지정안함 (인수는 크기를 주지 않습니다.)

   * 변수이름 IN 테이블이름.컬럼명%TYPE;

   * 변수이름 IN 테이블이름.컴럼명%TYPE := 값;

   * 변수이름 IN 테이블이름.컬럼명%TYPE DEFAULT 값;
  
2. OUT -> 호출자에게 제공
   
    * (프로시저 실행 시점에 OUT 매개변수를 변수 형태로 전달하고, 프로시저 실행부에서 이 매개변수에 특정 값을 할당, )

    * 변수이름 IN VARCHAR2;

    * 변수이름 IN 테이블이름.컬럼명%TYPE;

3. IN OUT -> 입력과 동시에 출력용으로 사용할 수 있다.

    * 변수이름 IN VARCHAR2;

    * 변수이름 IN 테이블이름.컬럼명%TYPE;
  
---
<br></br>

출처 : [https://goddaehee.tistory.com/163]