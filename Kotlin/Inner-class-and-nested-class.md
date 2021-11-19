# 내부(Inner) 클래스와 중첩(nested) 클래스

* 자바에서는 A_class 안에 B_class 정의 시 B_class는 자동으로 내부 클래스가 됨.

* Kotlin에서 내부 클래스를 정의하고 싶으면 `inner` 키워드를 명시적으로 사용해야 됨.

* 내부 클래스는 외부 클래스를 참조하게 할 수 있지만, 중첩 클래스는 그렇지 못함.

* ```Kotlin
    // inner class 내부 클래스
    class Outer {
        private val bar: Int = 1
        inner class Inner {
            fun foo() = bar
        }
    }

    val demo = Outer().Inner().foo() // == 1
  ```

* ```Kotlin
    // nested class 중첩 클래스
    class Outer {
        private val bar: Int = 1
        class Nested {
            fun foo() = 2
        }
    }

    val demo = Outer.Nested().foo() // == 2
  ```
<br></br>

* 내부 클래스의 경우 항상 외부 클래스의 객체를 참조하기 때문에 적절한 시점에 삭제되지 못하고 메모리 누수가 발생함.

* 특별한 경우가 아니라면 내부 클래스 사용을 지양하고 중첩 클래스를 사용하는 것이 권장