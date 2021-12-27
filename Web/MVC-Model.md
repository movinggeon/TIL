# MVC 란?

## M (model)

1. 사용자가 편집하길 원하는 모든 데이터를 가지고 있어야 함.
2. 뷰나 컨트롤러에 대해서 어떠한 정보도 알지 말아야 함.
3. 변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야 한다.

* DAO, VO class

<br>

## V (view)

1. 모델이 가지고 있는 정보를 따로 저장해서는 안된다.
2. 모델이나 컨트롤러와 같이 다른 구성요소들을 몰라야 한다.
3. 변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야 한다.

* JSP 페이지

<br>

## C (controller)

1. 모델이나 뷰에 대해서 알고 있어야 한다.
2. 모델이나 뷰의 변경을 모니터링 해야 한다.

* Model-2 방식에서 -> Java 소스

<br>
<br>

# [JSP] Model-1, Model-2

## Model-1

1. 사용자의 요청을 JSP가 전부 다 처리함.
2. 웹브라우저 사용자의 요청을 받은 JSP는 자바빈이나 서비스 클래스를 사용하여 웹브라우저가 요청한 작업을 처리하고 그 결과를 출력해줌.

<br>

* Model-1 : 개발속도가 빠르지만 유지보수 측면에서 불리함.(소,중형 프로젝트에서 사용)

## Model-2

1. 사용자 요청을 서블릿이 받음.
2. 서블릿은 해당 요청을 View로 보여줄것인지 Model로 보내줄것인지 정하여 전송함.
* View : 사용자에게 보여주는 역할만 담당함.
* Model : 실질적인 기능 구현.
<br>

* Model-2 : 개발확장, 유지보수가 쉬움. (중,대형 프로젝트에서 사용)