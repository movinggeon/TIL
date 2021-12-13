# GET 

* URL에 파라미터를 붙여서 전송함.
```html
http://ldg.github.com/index?param1=value1&param2=value2
```

* URL에 파라미터를 붙여 전송하기 때문에 body 영역을 사용하지 않음.
  
* URL에 데이터를 실어 보내기 때문에 대용량 전송을 하는데 제한이 있음

* 한번 전송시 URL 포함 255자 까지 전송가능.(HTTP/1.1에서는 2048자 까지 가능함)

<br></br>

# POST

* GET방식과 달리 body 영역에 데이터를 실어 보냄.

* body에 데이터를 실어 보내기 때문에 데이턴 전송량에 길이 제한이 없고 대용량 전송을 하는데 적합함

* body 영역 데이터 타입을 ``<Header>``영역 Content-Type에 명시 해주어야 됨.
```html
<!--ex-->
<head>
...
<meta charset="utf-8">
...
</head>
```

* GET방식과는 달리 보내는 데이터를 URL를 통해 볼 수 없어 보안적으로 안전하다곤 하지만 다른 툴을 사용하여 POST영역의 데이터를 확인이 가능하기 때문에 안심해서는 안됨.