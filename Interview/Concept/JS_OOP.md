# OOP(Object Oriented Programing)

---

## 캡슐화

- `캡슐화`란 하나의 객체가 특정한 목적을 해결하가 위해 변수, 함수를 하나로 묶는 것.
- 클래스를 만들 때 목적을 명확하게 하고 그에 따른 기능을 `관련성` 있게 변수나 함수를 만들 것.
- 데이터에 접근할 때 외부에서 직접적으로 접근하면 안되고 함수를 통해서 접근.
- JavsScript에서는 `private`한 변수 혹은 메소드가 없기 때문에 캡슐화를 통해 만들어준다.

## 상속화

- 상위의 부모 객체(개념)속성을 하위 객체(개념)가 물려받는 것.
- 상속은 객체 지향의 가장 큰 특징.
- 부모가 가지고 있는 속성(프로퍼티, 속성등)을 그대로 자식들이 사용 할 수 있고 재정의 가능.

## 추상화

- 예를 들어, 기린, 사자, 코끼리를 각각의 객체라고 하면 이 객체를 하나로 묶으려 할 때 `동물`이라는 추상적인 객체로 정의할 수 있다.
- 객체 지향에서는 객체에서 공통된 속성과 행위를 추출하는 것을 `추상화`라고 한다.

## 다형성

- 상속받은 기능을 변경하거나 확장하는 것.
- 코드의 재사용성이 높아져 코드의 길이가 감소하고 유지보수가 용이해짐

  #### 다형성 두가지

  1. 오버라이딩(OverRiding)

     부모클래스를 상속받은 자식 클래스에서 재정의 하는 것.

  2. 오버로딩(OverRoading)

     같은 클래스에서 같은 이름을 가진 메소드가 여러 개가 존재하고 있는 상태이다.
     메소드의 이름은 같아도 되지만 매개변수가 같으면 안된다.
     자바스크립트는 오버로딩을 할 순 없지만 `arguments`를 활용해 오버로딩을 `흉내`낼 수는 있다.
