* 기본적으로 ``<% %> ``이 아닌 HTML영역에 ``${ }``을 사용함.

<br>

## 1. 영역(Scope) 객체값 출력

* ``${key}`` : request, session, application 등 영역값 가져올때 쓰임.

```jsp
//ScopeEx.jsp

request.setAttribute("request", "request 영역 값 가져옵니다.");
sesseion.setAttribute("session", "session 영역 값 가져옵니다.");
application.setAttribute("application", "application 영역 값 가져옵니다.");

RequestDispatcher rd = request.getRequestDispatcher("Socpe_res.jsp");
rd.forward(request,response);
```

<br>

```jsp
//Scope_res.jsp

request 영역값 EL : ${request}
session 영역값 EL : ${session}
application 영역값 EL : ${application}
```

${영역Scope.key}<br>
➡️ 영역이 다른데 키값이 같을 경우 사용<br>

```jsp
//key 값은 request로 같다고 가정

request 영역값 EL : ${request} 
session 영역값 EL : ${sessionScope.request} 
application 영역값 EL : ${applicationScope.request} 
```

<br>

## 2. ``<form>`` 태그에서 가져와 출력

* ``${param.name}``으로 값 가져옴

```html
<!--paramForm.html-->

<form action = "param.jsp">
    이름<input type = "text" name = "name">
    생년월일<input type = "text" name = "birth">
    <input type = "submit" value = "전송">
```
<br>

```html
<!--param.jsp-->

사용자 이름 : %{param.name}
사용자 생년월일 : %{param.birth}
```

<br>

* 체크박스와 같이 여러개를 가져와야 할 경우 ``${paramValues.name[n]}``으로 값 가져옴

```html
<!--paramValuesForm.html-->
<form action = "paramValues.jsp" method = "post">
    운동<input type="checkbox" name="hobby" value="운동"/>
    공부<input type="checkbox" name="hobby" value="공부"/>
    코딩<input type="checkbox" name="hobby" value="코딩"/>
    <input type = "submit" value = "전송">
</form>
```

```html
<!--paramValues.jsp-->

사용자 취미: ${paramValues.hobby[0]} / ${paramValues.hobby[1]} / ${paramValues.hobby[2]}
```

---

* EL식 안에서 연산자 사용 가능!!