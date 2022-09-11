## Type 

### Primitive Type과 Reference Type
> Some types can have a special internal representation – for example, numbers, characters and booleans can be represented as primitive values at runtime – but to the user they look like ordinary classes.
> 
> https://kotlinlang.org/docs/basic-types.html
- 숫자, 문자, 불리언 같은 몇몇 타입은 내부적으로 특별한 표현을 가질 수 있다. 
- 코드상에서는 평범한 레퍼런스 타입처럼 보이지만 런타임에는 원시값으로 표현될 수 있다. (Kotlin 컴파일러가 필요에 따라서 적절하게 처리해준다.)

### Exception Type
- [Nothing](https://kotlinlang.org/docs/exceptions.html?_gl=1*11o9135*_ga*MTU4NDQ5MTk4NC4xNjYwMzg4OTY5*_ga_9J976DJZ68*MTY2MjgyNzUyMC4zLjEuMTY2MjgyOTcyMC4wLjAuMA..&_ga=2.253443593.1697541299.1662827520-1584491984.1660388969#the-nothing-type)
  - `throw` 표현식에는 `Nothing` 이라는 타입이 사용되며, 이 타입은 값이 없고 도달할 수 없는 코드 위치를 표시하는데 사용된다.
  - 반환값이 `Nothing`인 함수를 호출할 때 컴파일러는 이러한 함수를 넘어서 실행이 계속되지 않는다는 정보를 사용한다.
 
### Platform Type
- Kotlin이 `null`관련 정보를 알 수 없는 타입으로 런타임에서 Exception이 발생할 수 있다.

### Type Casting
- Java에서 Primitive Type간의 변환은 암시적으로 이루어지지만, Kotlin에서는 명시적으로 변환해야 한다.
  ```kotlin
  val i = 3
  val l = i.toLong()
  ```
- Java에서 일반 타입의 경우 `instanceof`를 이용하여 타입을 확인하고 명시적으로 캐스팅 할 수 있다.
- Kotlin에서는 `is`를 활용해서 타입을 확인하고 `as`를 이용해서 캐스팅 할 수 있다.
  - `is`는 `instanceof`와 동일하며, Kotlin에서 `is` 컨텍스트 하위의 `as`는 생략될 수 있다. (Kotlin의 스마트 캐스트)
  - Java에서는 Java 17 버전 이후에 도입된 `instanceof` 패턴 매칭을 사용할 수 있다.
  - Java에서는 `instanceof`에 `not`을 붙이기 위해서는 수식 전체를 감싸고 앞에 `!`를 붙여야 한다.
  - 반면 Kotlin에서는 `!is`를 사용하여 `instanceof`에 `not`을 붙일 수 있다.
- `as?`를 사용하면 대상이 `null`이거나 캐스팅에 실패하면 `null`을 반환한다.

### Any
- Any는 Java에서의 Object 타입과 동일하다. (모든 객체의 최상위 타입)
  - Primitive Type의 최상위 타입도 Any이다.
- Any 자체로는 `null`을 포함할 수 없기 때문에 `null`을 포함하고 싶다면 Any?로 표현해야한다.
- Any도 Object와 마찬가지로 기본적으로 `equals`, `hashCode`, `toString`을 구현하고 있다.

### Unit
- Unit은 Java의 `void`와 동일하다.
- `void`와 다르게 Unit은 그 자체로 타입 파라미터로 사용할 수 있다.
- FP에서 Unit은 단 하나의 인스턴스만 갖는 타입을 의미하며, Kotlin의 Unit은 실제 존재하는 타입이라는 것을 표현한다.


### String Interpolation, String Indexing
- Kotlin에서는 String Interpolation을 지원한다.
  ```kotlin
  val name = "Kotlin"
  println("Hello, ${name}")
  ```
- 중괄호를 생략할 수도 있지만 중괄호를 사용하는 것이 가독성 및 일괄변환, 정규식 활용 측면에서 더 좋다.
- Kotlin에서는 여러줄에 걸친 문자열을 작성할 떄 `"""`를 사용한다. (Java에서는 Java 14부터 지원한다.)
- Kotlin에서는 String Indexing을 지원한다. (Java에서는 `charAt` 메서드를 통해 접근한다.)
  ```kotlin
  val str = "Kotlin"
  println(str[0]) // K
  println(str[1]) // o
  println(str[2]) // t
  println(str[3]) // l
  println(str[4]) // i
  println(str[5]) // n
  ```
