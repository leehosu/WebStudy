# Classes

- ES6 클래스는 프로토타입 기반 객체지향 패턴을 더 쉽게 사용할 수 있는 대체재이다.
- 클래스 패턴 생성을 더 쉽고 단순하게 생성할 수 있어서 사용하기도 편하고 상호운용성도 증가된다.
- function식과 비슷하게, class 식을 사용하는데 named 또는 unnamed일 수 있다.

#### 기본 구문
```js
var MyClass = class [className] [extends] {
    //class Body
};
```
- class 식은 `class`문과 구문이 비슷하다.
- class식의 경우 class 명을 생략할 수 있는데 class문으로는 할 수 없다.

## 예제
#### 간단한 class 식
```js
var Foo = class {
    constructor() {}
    bar() {
        return "Hello World";
    }
};

var instance = new Foo();
instance.bar(); //"Hello World!"
Foo.name; //""
```

#### named class 식
```js
var Foo = class NamedFoo {
    construcor() {}
    whoIsThere() {
        return NamedFoo.name;
    }
}

var bar = new Foo();
bar.whoIsThere(); //"NamedFoo"
NamedFoo.name;  //Reference Error : NamedFoo가 정의되지 않았다.
Foo.name; //"NamedFoo"
```
