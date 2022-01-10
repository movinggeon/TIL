# 객체 생성 (bean)

* 자바의 경우
    ```java
        package package1;
        class1 bb1 = new bb();
    ```

* jsp 액션 태그의 경우
    ```jsp
    <jsp:useBean id = "bb1" class="package1.class1">

    ...

    <jsp:setProperty name = "bb1" property = "*"> // bb1.setName("넘어오는 이름"), bb1.setAge("넘어오는 나이")

    ...

    이름은 <jsp:getProperty name = "bb1" property= "name"> //bb1.getName();
    ```

* 스프링에서 객체 생성시 bean 객체라고 표현함.<br>
  표현방법은 xml 태그를 사용 (들어가는 곳도 xml파일)

    ```xml
        <bean id="classBean" class="package1.bb1"></bean>
    ```

## 스프링 빈 설정 방법

* [**참고 페이지**](https://atoz-develop.tistory.com/entry/Spring-%EB%B9%88%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-3%EA%B0%80%EC%A7%80-%EB%B0%A9%EB%B2%95-XML-JAVA-Component-Scan)