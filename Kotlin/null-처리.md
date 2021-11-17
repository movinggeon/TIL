
## Null이 될 수 있는 type
* Kotlin에서는 null을 명시적으로 표현해야 함
* **?** 연산자 사용
* ```Kotlin
  //ex)
  fun strLenSafe(s: String?): Int = if (s != null) s.length else 0
  ```

---
<br></br>

## Null safe operator

* null을 안전하게 처리하기 위해 **?.** 연산자 사용

* ```Kotlin
  //ex)
  fun printAllCaps(s: String?) { val allCaps: String? = s?.toUpperCase() println(allCaps) }
  ```
* 앞의 변수가 **null이 아닐 때만** 오른쪽 함수 실행, null이면 **null 반환**
* property 접근시에도 **?.** 연산자로 처리가능
  
* ```Kotlin
    //ex)
    val country = this.company?.address?.country
  ```
---
<br></br>

## Elvis operator

* null인 경우 default 값을 주고 싶은 경우 **?:** 연산자 사용
* 우항으로 **return, throw** 가능!

* ```Kotlin
    //ex)
    fun getName(str: String?) { val name = str ?: "Unknown" }
    ```