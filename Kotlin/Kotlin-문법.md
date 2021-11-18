## val , var
---
>val &nbsp;&nbsp;&nbsp; : 변하지 않는 변수 <br></br>
>var &nbsp;&nbsp;&nbsp; : 변하는 변수

<br></br>

## 변수 선언
---
* **type**을 명시 해주어야 됨
  
* ```Kotlin
    //ex)
    var i : Int = 111

    //배열
    var intArr : IntArray = IntArray(10)

    //컬렉션
    var mutableList = mutableListOf<Int>()
    mutableList.add(5)
    mutableList.add(10)

    //맵
    var mutableMap = mutableMapOf<String, String>()
    mutableMap.put("변수1","값1")
    mutableMap.put("변수2","값2")
  ```
---
<br></br>

## 함수 선언
---
* 코드를 분류하기 위해 사용한다고 생각하기

* ```Kotlin
    //입력값 있는 함수
    fun functionName(param1 : String, param2 : String){

    }

    functionName("인자1","인자2")

    //출력값 있는 함수
    fun getPi() : Double { 
        return 3.141592
    }

    var pi = getPi()
  ```
---
<br></br>

## 클래스
* 변수(property)와 함수(method)의 모음
* companion object : 클래스를 초기화 하지 않고 바로 실행 가능!
  
* ```Kotlin
    //일반 class
    class 클래스명 {

        var variable : String = " "; //변수(property)

        fun function() { //함수(method)
            var variable local = " ";
        }
    }

    //companion object
    class 클래스명 {
        companion object{
            fun d(tag : String, msg : String){
                print("[$tag] : $msg")
            }
        }
    }

    //클래스 사용
    //1.초기화
    var cls = 클래스명() // 인스턴스 : 메모리에 로드되어 있는 클래스

    cls.variable
    cls.function()

    //2.companion object 사용
    Log.d("태그","메세지")

  ```
---
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
---
* UI자원을 다루기 위한 방법
* 안드로이드 OS 는 UI 자원에 Main Thread와 Sub Thread가 동시 접근하여 동기화 이슈를 발생시키는 것을 방지시키기 위해 UI 자원 사용은 UI Thread에서만 가능하도록 만듦.

출처: https://solbel.tistory.com/761 [개발자의 끄적끄적]

---
<br></br>