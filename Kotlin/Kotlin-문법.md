## val , var
---
>val &nbsp;&nbsp;&nbsp; : 변하지 않는 변수 <br></br>
>var &nbsp;&nbsp;&nbsp; : 변하는 변수

<br></br>

## R.id-접두어 의미 
---
```Kotlin
val tt : TextView = findViewById(R.id.TextTest)
```
* R &nbsp; : 리소스를 관리하는 클래스
* id &nbsp; : 그 안에 리소스 아이디를 관리하는 클래스를 추가
---
<br></br>

## runOnUiThread 란?

* UI자원을 다루기 위한 방법
* 안드로이드 OS 는 UI 자원에 Main Thread와 Sub Thread가 동시 접근하여 동기화 이슈를 발생시키는 것을 방지시키기 위해 UI 자원 사용은 UI Thread에서만 가능하도록 만듦.

출처: https://solbel.tistory.com/761 [개발자의 끄적끄적]

---
<br></br>