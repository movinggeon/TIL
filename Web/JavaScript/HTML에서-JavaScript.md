# inline 방식

* html 태그에 직접 자바스크립트를 기술하는 방식
* 장점 : 태그에 연관된 스크립트가 분명하게 드러난다.
* 단점 : 정보와 제어가 섞여 있기 때문에 정보로서의 가치가 떨어짐.

```html
<!DOCTYPE html>
<html>
<body>
    <input type="button" onclick="alert('Hello world')" value="Hello world" />
</body>
</html>
```

<br>

# script

* <script></script>태그를 만들어서 태그 안에 자바스크립트 코드를 삽입하는 방식.
* html 태그와 js 코드를 분리할 수 있음.

```html
<body>
    <script>
        window.alert("안녕 스크립트"); <!--window 객체는 생략가능!-->
        <!-- alert("안녕 스크립트"); -->
    </script>
</body>
```

## (JavaScript)property란?

* https://m.blog.naver.com/magnking/220966405605