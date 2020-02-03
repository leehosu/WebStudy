# This Binding

- `Binding`이란 함수 호출과 실제 함수를 연결하는 방법이다.
- 즉 함수를 호출하는 부분에 함수가 위치한 메모리 번지를 연결시켜 주는 것이다.
- 자바스크립트에서 함수를 호출 할 때는 암묵적으로 `arguments` 객체 및 `this` 변수가 함수 내부로 전달된다.

- JavaScript의 `this`는 함수 호출 패턴에 따라 `this`가 어떤 객체의 `this`가 될지 정해짐.

## 함수 호출과 `this`

1 ) 객체 내부의 함수인 메소드 내부에서 사용된 `this`는 해당 메소드를 호출한 객체로 `binding` 된다.

```js
var obj1 = {
  name: "hosu",
  sayName: function() {
    console.log(this.name);
  }
};

var obj2 = {
  name: "lee"
};

obj2.sayName = obj1.sayName;

console.log(obj1.sayName()); //"hosu"
console.log(obj2.sayName()); //"lee"
```

2. 함수를 호출 하는 경우는, 해당 함수 내부 코드에서 사용된 `this`는 전역 객체에 `binding` 된다.
   (브라우저에서 JavaScript를 실행하는 경우의 전역 객체는 `window`이다.)

```js
var global = "a";

function myFunction() {
  var global = "b";

  console.log(this.global); //"a"
  console.log(this); // window 객체가 출력
}

myFunction();
```

```js
var value = 100;

var myObject = {
  value : 1;

  func1 : () => {
    this.value += 1;
    console.log(this.value); // 2

    func2 : () => {
      this.value += 1;
      console.log(this.value); //101

      func3 : () => {
        this.value += 1;
        console.log(this.value); // 102
      }
      func3();
    }
    func2();
  }
}

myObject.func1();
```

3. 생성자 함수 호출 할 때 각 매개변수값이 `binding` 된다.

```js
var Person = function(name) {
  if (name.length == 0) {
    this.name = Person.prototype.name;
  } else {
    this.name = name;
  }
};

Person.prototype.name = "lake";

var hosu = new Person("hosu");
var lake = new Person("");

console.log(hosu.name); // "hosu"
console.log(lake.name); // "lake"
```

##### Binding 메커니즘

1. `new` 키워드를 사용하면 생성자 함수 코드가 실행되기 전 빈 객체가 생성됨.
2. 빈 객체가 `생성자` 함수가 새로 생성하는 객체이며, `this`에 객체가 `binding`됨.
3. 생성된 빈 객체는 생성자 함수의 `prototype` 객체를 자신의 `prototype`으로 결정

- 생성자 함수를 사용할것임에도 `new`를 안붙이게 되면 함수 호출로 간주하여 `undefined`를 출력한다.

## this 메소드

##### apply 메소드

```js
var Person = function(name) {
  this.name = name;
};

var obj1 = {};

Person.apply(obj1, ["hosu"]);
console.log(obj1); // Object{name: "hosu"}
```

- 첫번째 매개변수로 빈 객체(this binding 객체), 두번째 매개변수로 매개변수 값

##### call 메소드

```js
var Person = function(name, gender) {
  this.name = name;
  this.gender = gender;
};

var hosu = {};

Person.call(hosu, "hosu", "man");

console.log(hosu); // Object{name: "hosu", gender: "man"}
```

- 첫번째 매개변수는 바인딩할 객체, 두번째 매개변수부터 매개변수 값
