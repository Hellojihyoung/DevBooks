- 유연성이 극대화된 시스템 
   : 소스 코드 의존성이 추상(abstraction)에 의존하며 구체(concretion)에는 의존하지 않는 시스템 

- 우리가 의존하지 않도록 피하고자 하는 것은 바로 변동성이 큰(volatile) 구체적인 요소다.
   : 구체적인 요소 : 자주 변경될 수 박에 없는 모듈들이다.


### 📕 안정된 추상화

- 인터페이스는 구현체보다 변동성이 낮다.
- 안정된 SW 아키텍처는 변동성이 큰 구현체에 의존하는 일을 지양하고, 안정된 추상 인터페이스를 활용해라.

아래는 DIP 에서 전달하려는 코딩 실천법이다.

  1. 변동성이 큰 구체 클래스를 참조하지 말아라
    - 대신 추상 인터페이스를 참조해라.
    - 추상 팩토리를 사용해라.
    
    
  2. 변동성이 큰 구체 클래스로부터 파생하지 말아라.
    - 상속을 유의해서 사용하라.
    
  3. 구체 함수를 오버라이드 하지 말아라.
    - 대체로 구체 함수는 소스 코드 의존성을 필요로 한다.
    - 오버라이드 하면 의존성을 상속하게 된다.
    - 의존성을 제거하려면, 추상 함수로 선언하고 구현체들에서 각자의 용도에 맞게 구현해야 한다.
  4. 구체적이며 변동성이 크다면 이름을 언급하지 말아라.

##### * 추상 팩토리 패턴 : 상세화된 서브클래스를 정의하지 않고도 서로 관련성이 있거나 독립적인 여러 객체의 군을 생성하기 위한 인터페이스를 제공하는 패턴

<br>

### 📗 팩토리
변동성이 큰 구체적 객체는 생성할때 주의한다.
![](https://velog.velcdn.com/images/hellojihyoung/post/fbd5c783-5cfe-4ac4-bf2d-7a2eb2188d64/image.png)

- 위 그림에서 곡선은 시스템을 구체적인 것들로 부터 추상적인 것들을 분리한다.
- 소스 코드 의존성은 해당 곡선과 교차할 때 모두 한 방향, 즉 추상적인 쪽으로 향한다.
- 곡선은 시스템을 추상 컴포넌트, 구체 컴포넌트로 분리한다.
  - 추상 컴포넌트는 애플리케이션의 모든 고수준 업무 규칙을 포함한다.
  - 구체 컴포넌트는 업무 규칙을 다루기 위해 필요한 세부사항을 포함한다.
- 소스 코드 의존성은 제어흐름과는 반대 방향으로 역전된다. → _**의존성 역전(Dependency Inversion)**_


<br>

### 📙 구체 컴포넌트
구체 컴포넌트에 구체적인 의존성이 없어야 하지만, DIP 위배를 모두 없앨 수는 없기 때문에 Main 함수에 구체 컴포넌트를 최소한 하나는 포함해준다.

<br>

### 📘 결론
- DIP는 아키텍처 다이어그램에서 가장 눈에 드러나는 원칙이 될것이다.
- 의존성은 아키텍처 경계를 기준으로, 더 추상적인 엔티티가 있는 쪽으로만 향한다.

<br>


### 📚 Reference
- Clean Architecture : 소프트웨어 구조와 설계의 원칙
