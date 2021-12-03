# BOM

* BOM : Browser Object Model
  
* 웹브라우저의 창이나 프래임을 추상화해서 프로그래밍적으로 제어할 수 있도록 제공하는 수단
  
* BOM의 전역 객체 : Window

<br>

---
## alert

* 경고창이 뜸.
  
* 예제는 HTML에서-JavaScript 참고

---
## confirm

* 확인을 누르면 true, 취소를 누르면 false

```html
<body>
	<input type="button" value="check" onclick="checkBoolean()">
	<script type="text/javascript">
		function checkBoolean() {
			if(confirm('ok?')){
				alert('true');
			}else{
				alert('false');
			}
		}
	</script>
</body>
```

* check 버튼을 누르면 ok? 라는 confirm창이 뜨고 확인을 누르면 true 경고창, 취소를 누르면 false 경고창이 뜸.

---
## prompt

```html
    <body>
        <input type="button" value="check" onclick="func_prompt()" />
        <script>
            function func_prompt(){
                if(prompt('id?') === 'egoing'){
                    alert('welcome');
                } else {
                    alert('fail');
                }
            }
        </script>
    </body>
```
1. check 버튼을 누르면 func_prompt() 메소드가 호출 됨.
   
2. id?라도 쓰여진 입력창이 호출되고 client는 해당 입력창에 typing 가능.
   
3. client가 egoing이라는 문자열을 입력했을시 welcome 경고창이 뜸.
   
4. egoing이 아닐시 fail 경고창이 뜸.
---
## location 객체

* 현재 윈도우의 문서가 위치하는 URL을 알아내는 방법<br>
  ``console.log(location.toString(), location.href);``

* location 객체는 URL을 의미에 따라서 별도의 프로퍼티로 제공 함.<br>
  ``console.log(location.protocol, location.host, location.port, location.pathname, location.search, location.hash)``

* 현재 문서를 다른 URL로 이동<br>
  ```html
  location.href = 'http://ldg.net'; <!--아래와 같은 기능-->
  location = 'http://ldg.net';
  ```

* 페이지 리로드<br>
  ``location.reload();``
---

## window.open

```html
<body>
<ul>
    <li>
        첫번째 인자는 새 창에 로드할 문서의 URL이다. 인자를 생략하면 이름이 붙지 않은 새 창이 만들어진다.<br />
        <input type="button" onclick="open1()" value="window.open('demo2.html');" />
    </li>
    <li>
        두번째 인자는 새 창의 이름이다. _self는 스크립트가 실행되는 창을 의미한다.<br />
        <input type="button" onclick="open2()" value="window.open('demo2.html', '_self');" />
    </li>
    <li>
        _blank는 새 창을 의미한다. <br />
        <input type="button" onclick="open3()" value="window.open('demo2.html', '_blank');" />
    </li>
    <li>
        창에 이름을 붙일 수 있다. open을 재실행 했을 때 동일한 이름의 창이 있다면 그곳으로 문서가 로드된다.<br />
        <input type="button" onclick="open4()" value="window.open('demo2.html', 'ot');" />
    </li>
    <li>
        세번재 인자는 새 창의 모양과 관련된 속성이 온다.<br />
        <input type="button" onclick="open5()" value="window.open('demo2.html', '_blank', 'width=200, height=200, resizable=yes');" />
    </li>
</ul>
 
<script>
function open1(){
    window.open('demo2.html');
}
function open2(){
    window.open('demo2.html', '_self');
}
function open3(){
    window.open('demo2.html', '_blank');
}
function open4(){
    window.open('demo2.html', 'ot');
}
function open5(){
    window.open('demo2.html', '_blank', 'width=200, height=200, resizable=no');
}
</script>
</body>
```

* window.open 자료 : https://opentutorials.org/course/1375/6651