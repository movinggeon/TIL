# CSS

* html ``<head>`` 안에 ``<style>``태그를 선언하여 사용.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      h2{color:blue}
    </style>
  </head>
  <body>
    <h1 style="color:red">Hello World</h1>
    <h2>Hello world</h2> <!--파랑색으로 출력됨-->
  </body>
</html>
```

* id 값으로 사용하기 위해서는 **#** 을 붙이면 됨.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      #select{
        font-size:50px;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>HTML</li>
      <li id="select">CSS</li>
      <li>JavaScript</li>
    </ul>
  </body>
</html>
```

* class 값으로 사용하기 위해서는 **.** 을 붙이면 됨

```html
<html>
  <head>
    <style>
      .select{
        font-size:50px;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>HTML</li>
      <li class="select">CSS</li>
      <li>JavaScript</li>
    </ul>
  </body>
</html>
```

* 외부로 파일 빼는 법

1. ``<link rel="stylesheet" href="style.css">`` -html태그로 하는법

2. ```html
    <style>
    @import url("style.css")
    </style>
   ``` 
   -css로 style태그에서 하는법