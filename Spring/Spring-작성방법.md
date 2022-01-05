# 작성방법

## 작성방법 - 1

* 기존 eclipse (Dynamic WEB Project)에 spring library 를 직접 추가

    * WEB-INF -> lib 디렉터리에 .jar 추가

<br>
<br>
<br>
<br>

## 작성방법 -2 (이걸 주로 사용함)

* 기존 eclipse에 STS (Spring Tool Suite)를 plug-in하기

* pom.xml 이라는 "환경설정파일"에 필요한 내용을 써 놓으면 스프링이 알아서 다운로드

* spring project + pom.xml 에 필요한 라이브러리를 받도록 적어줌

    * (참고) 이 방식으로 작성하면 작성하자마자 프로젝트에 액박이 뜸 , 그리고 잠시 기다리면 액박이 사라짐

        * why?<br>
            필요한 라이브러리를 외부저장소로부터 공급받음.<br> 
            받는 시간 걸림, 받은 것이 적용되는 시간 걸림.

<br>
<br>
<br>
<br>

## 작성방법 -3

* STS 툴 다운