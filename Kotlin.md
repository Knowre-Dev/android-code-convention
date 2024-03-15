✓ 클래스의 작성 순서는 아래와 같이 작성한다.
  - Property declarations and initializer blocks
  - Secondary constructors
  - Method declarations
  - Companion object
    
✓ 인터페이스를 구현하는 클래스의 프로퍼티 및 함수는 해당 인터페이스에 선언된 프로퍼티와 함수의 순서와 동일하게 작성한다.

✓ 클래스 헤더 작성은 아래를 따른다.
  - 인자가 적을 경우 한줄에 작성한다.
  ``` kotlin
  class Person(id: Int, name: String)
  ```
  - 인자가 여러개일 경우 개인의 판단하에 아래와 같이 인자들을 각각 줄바꿈해 작성한다.
  ``` kotlin
  class Person(
      id: Int,
      name: String,
      surname: String
  ) : Human(id, name) { /*...*/ }
  ```
  - 클래스가 여러개의 인터페이스를 구현할 경우 아래와 같이 인터페이스들을 각각 줄바꿈해 작성한다.
  ``` kotlin
  class Person(
      id: Int,
      name: String,
      surname: String
  ) : Human(id, name),
      KotlinMaker { /*...*/ }
  ```
  - 클래스 헤더가 길어질 경우 본문과의 구별을 위해 클래스를 여는 괄호 아래에 공백칸 하나를 추가한다.
  ``` kotlin
  class MyFavouriteVeryLongClassHolder :
      MyLongHolder<MyFavouriteVeryLongClass>(),
      SomeOtherInterface,
      AndAnotherOne {
  
      fun foo() { /*...*/ }
  }
  ```

✓ 조건문은 작성은 아래를 따른다.
  - && 을 사용할 경우 실패할 확률이 높은 조건을 맨 앞에 작성하고, || 를 사용할 경우는 성공확률이 높은 조건을 맨 앞에 작성한다.
  - 조건식이 여러개일 경우 아래와 같이 조건들을 줄바꿈해 작성한다.
  ``` kotlin
  if (!component.isSyncing &&
      !hasAnyKotlinRuntimeInScope(module) ||
      isConfigurableComponent
  ) {
      return createKotlinNotConfiguredPanel(module)
  }
  ```

✓ 함수 콜
  - 아규먼츠가 길어질 경우 줄바꿈을 사용하되, 비슷한 성격의 아규먼츠는 같은 라인에 작성한다.
  ``` kotlin
  drawSquare(
      x = 10, y = 10,
      width = 100, height = 100,
      fill = true
  )
  ```

✓ 람다
  - 람다 파라미터가 길어질 경우 -> 를 마지막 마지막 파라미터에서 줄바꿈해 작성한다.
  ``` kotlin
  foo {
     context: Context,
     environment: Env
     ->
     context.configureEnv(environment)
  }
  ```

---

✓ data class 는 아래와 같은 조건에서만 사용한다.
  - 모든 변수가 Immutable 일 경우 (var, MutableList, MutableSet 등등이 포함되면 data class 를 사용하지 않는다.)

✓ arguments hint 를 적극적으로 사용한다.
