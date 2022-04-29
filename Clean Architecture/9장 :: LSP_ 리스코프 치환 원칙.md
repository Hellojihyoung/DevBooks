리스코프(Barbara Liskov)는 하위 타입(subtype)을 아래와 같이 정의 했다.

- S 타입의 객체 o1에 대응하는 T타입 객체 o2가 있다. → o1: S, o2: T
- T 타입을 이용해서 정의한 모든 프로그램 P에서 o2의 자리에 o1을 치환해도 P의 행위가 변하지 않는다면, S는 T의 하위 타입이다.

### 📕 상속을 사용하도록 가이드하기
![](https://velog.velcdn.com/images/hellojihyoung/post/bb4294c7-1d44-4042-902f-8b66fe44708b/image.png)

위의 그림은 LSP 를 만족한다.
- Billing 애플리케이션의 행위가 License 하위 타입 중 무엇을 사용하는지에 전혀 의존하지 않는다.
- 하위 타입은 모두 License 타입을 치환할 수 있다.


<br>

### 📗 정사각형 / 직사각형 문제
![](https://velog.velcdn.com/images/hellojihyoung/post/c991244d-c281-4962-afb7-88cb0fb66842/image.png)

위의 그림은 LSP 를 위반한다.

- Square는 Rectanglge의 하위 타입으로 적합하지 않다.

   - Rectangle의 높이와 너비는 서로 독립적으로 변경될 수 있는 반면, Square의 높이와 너비는 반드시 함께 변경되기 때문이다.
   - 이를 해결하기 위해 조건문을 사용해 Rectangle이 실제로는 Square인지 검사한다.
     - 이렇게 되면 User의 행위가 사용하는 타입에 의존하게 되므로, 결국 타입을 서로 치환할 수 없게 된다.

<br>

### 📙 LSP와 아키텍처
아키텍처 관점에서 LSP를 이해하는 최선의 방법은 이 원칙을 어겼을 때 시스템 아키텍처에서 무슨 일이 일어나는지 관찰하는 것이다.

<br>

### 📘 LSP 위배 사례
LSP 를 위반할 경우 모듈을 새로 만들어 버그를 해결할 수 있도록 한다.
단순히 이미 있는 모듈에 코드를 추가하는 방법은 지양한다.

<br>

### 📒 결론
- LSP 는 아키텍처 수준을 확장해야 한다.
- 치환 가능성을 위배하지 않도록 해야한다.



<br>




### 📚 Reference
- Clean Architecture : 소프트웨어 구조와 설계의 원칙
