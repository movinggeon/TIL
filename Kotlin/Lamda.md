# Lamda

### Lamda

1. 함수를 선언하지 않고 곧바로 식으로 전달돼서 표현
   
2. 파라미터는 ``->`` 왼쪽에 선언됨.

3. ``->`` 오른쪽에는 function 작동.

4. 람다 식은 ``{ }``로 시작하고 끝남.

```kotlin
//ex
fun sayHello (name: String) {
   println("Hello, $name!")
}
sayHello("LDG")
```
⬇️
```kotlin
val sayHello = { name: String -> println("Hello, $name!")}
sayHello("Nachoi")
```
