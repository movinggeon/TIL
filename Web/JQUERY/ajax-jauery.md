# $.ajax 메소드

* HTTP 요청을 직관적으로 제공

* ``$.ajax([옵션])``

* 예시<br>
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://code.jquery.com/jquery-1.12.4.min.js"></script>
    <script>
        $(function(){
            //id가 requestBtn 인 버튼 클릭시 이벤트 호출
            $("#requestBtn").on("click", function(){
                $.ajax({
                    url: "http://localhost:8000/test/ajax.html", //클라이언트가 요청을 보낼 url
                    // data: {
                    //     title: "안녕",
                    //     discription : "jquery-ajax야"
                    // },
                    // type: "GET",
                    // dataType: "json"
                })

                //요청 성공시 done 메소드 호출 됨
                .done(function(){
                    alert("success"); 
                })
            })
        })
    </script>
</head>
<body>
    <button id="requestBtn">눌러봐</button>
</body>
</html>
```

## 해봐야 할 일

1. $.ajax를 통해 다른 페이지로 데이터 넘기기