## Chapter 02 : 객체의 생성과 파괴

<br>



#### 클라이언트가 클래스의 인스턴스를 얻는 수단

- public 생성자

  ```java
  class Item {
      public Item() { } 
  }
  ```

  ```java
  Item instance = new Item();
  ```

- 정적 팩토리 메소드 (static factory method)

  ```java
  class Item {
      Item staticInstance = new Item();
      
      static Item getInstance() {
          return staticInstance; 
      }
  }
  ```

<br>



#### 정적 팩토리 메소드 방식이 생성자보다 좋은 이유

- 이름 설정
  - 객체 특성을 표현할 수 있는 이름을 인스턴스에 붙여서 구분 가능 
- 인스턴스를 미리 만들어놓고 호출될 떄마다 인스턴스를 새로 생성하지 않아도 된다
  - 생성비용이 큰 객체를 자주 요청하는 경우
  - 불필요한 객체 생성을 피할 수 있다
- 반환 타입의 하위 클래스 객체를 반환 가능
  - 객체 지향적. 유연성
  - 