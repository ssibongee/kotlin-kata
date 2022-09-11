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
