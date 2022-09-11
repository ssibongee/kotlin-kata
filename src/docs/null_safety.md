## Null Safety with Kotlin
https://kotlinlang.org/docs/null-safety.html#nullable-types-and-non-null-types

- Kotlin에서 NullPointerException이 발생할 수 있는 경우는 다음과 같다.
  - 명시적인 NullPointerException 호출
  - `!!` 연산자의 사용 (`null`이면 NullPointerException 발생)
    ```kotlin
    val l = b!!.length
    ```
  - 초기화 관련 데이터 불일치 
  - Java 코드와 상호 운용했을 때 외부 Java 코드로 인한 NullPointerException 발생 
- 코틀린에서 기본적으로 `null`을 허용하지 않는다.
  - `null`을 허용하려면 타입 뒤에 `?`를 붙여야 한다.
    ```kotlin
    var a: String = "abc"
    a = null // 컴파일 에러
    
    var b: String? = "abc"
    b = null // OK
    ```
- `nullable` 변수에 대해서는 `?.` 연산자를 이용해서 안전하게 호출할 수 있다.
  - `?.` 연산자는 `null`이 아닐 때만 호출하고, 체이닝 요소들 중에서 어떠한 것이라도 `null`이면 `null`을 반환한다.
    ```kotlin
    person?.department?.head?.name
    ```
- `?:`는 Elvis 연산자라고하며 왼쪽의 표현식이 `null`이 아니면 그대로 반환하고, `null`이면 오른쪽의 표현식을 반환한다.
  ```kotlin
  val l = b?.length ?: -1
  ``` 
