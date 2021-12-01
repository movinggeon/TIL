# HTML

* HTML : Hyper Text Markup Language

```html
<!DOCTYPE html>  <!--HTML5로 시작한다는 뜻-->
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <h1> Hello HTML!</h1>
</body>
</html>
```

* 현재 HTML5를 사용

<br></br>
  
# HTML 태그

* ``<br>`` : Enter(줄 바꿈)

* ``&nbsp;`` : Space Bar(띄워쓰기)
  
* ``<b>`` : bold
  
* ``<i>`` : italic
  
* ``<strike>`` : 취소선 &nbsp;&nbsp;&nbsp;&nbsp;ex) ~~예시~~
  
* ``<u>`` : underline
  
* ``<code> text_1 <sub> text_2 </sub><sup> text_3 </sup> </code>`` : typing글씨체 &nbsp;&nbsp;ex) log 함수 쓸 경우 

* ``<p>`` : 문단 <br>
  
> 1. ``<p align = "value">`` : 정렬

* ``<pre>`` : 전체 줄 바꿈(줄 바꿈을 많이해야될 때 br태그를 일일이 할 필요가 없음)

* ``<marquee>`` : 전광판처럼 글자가 이동함

> 1. ``<marquee direction = "value">`` : 방향 설정

* ``<table>`` : 테이블
1. 
    ```html
    <!--ex-->
    <table border = 2>
            <tr>
                <td>hong</td><td>choi</td>
            </tr>
            <tr>
                <td>kim</td><td>park</td>
            </tr>
    </table>
    ```
<center>⬇️
    <table border = 2>
        <tr>
            <td>hong</td><td>choi</td>
        </tr>
        <tr>
            <td>kim</td><td>park</td>
        </tr>
    </table>
</center>

* ``<a>`` : 링크
> 1. ``<a href = "URL"></a>`` : 해당 URL로 이동