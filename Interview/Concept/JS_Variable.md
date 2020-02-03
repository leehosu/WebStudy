# 변수

## 식별자

- `문자` , `_` , `$` , `숫자(0-9)`로 식별한다.
- JavaScript가 대소문자를 구분하기에, 문자는 "`A`"부터 "`Z`"(`대문자`)와 "`a`"부터 "`z`"(`소문자`)까지 모두 포함한다.

## 변수의 종류

```js
var a = ""; // 문자열
var b = 0; // 숫자
var c = false; // 불린
var d = null; // 널
var e = undefined; // 언디파인드
var f = []; // 배열
var g = {}; // 객체
var h = function() {}; // 함수
```

## `var` vs `let` vs `const`

- `var`는 일반적인 변수 선언 방식인데 중복되어도 값이 할당된다 -> 사용지양
- `let` 변수 선언 방식인데 중복되면 값이 할당되지 않는다.
- `const` 변수 선언 방식인데 `변수 재선언`, `변수 재할당` 모두 되지 않는다.

# 변수 할당

- 초기값이 지정되지 않은 변수는 `undefined` 값을 갖는다.
- 선언되지 않은 변수에 접근하려고 하면 `Reference Error` 예외가 발생한다.

```js
var a;
console.log("a 값은 " + a); // "a 값은 undefined"

console.log("b 값은 " + b); // b 값은 undefined
var b;

console.log("c 값은 " + c); // ReferenceError

let x;
console.log("x 값은 " + x); // x 값은 undefined

console.oog("y 값은 " + y); // ReferenceError 예외 던짐
let y;
```

# scope

##### `function scope`

- function 내부에서 선언한 변수는 `지역 변수(function scope)`로 해당 함수 내에서만 접근 및 호출이 가능하다.
- 정의한 함수 밖에서 호출하려는 경우, 정의되지 않는 변수를 참조하려고 하여 `Reference Error`가 발생한다.

#### `global scope`

- function 밖에서 선언한 변수는 `전역 변수(global scope)`로 사용되며, 해당 페이지 내의 어떤 함수에서든 접근 및 호출 할 수 있다.

```js
if (true) {
  var x = 5;
}
console.log(x); //5
```

```js
if (true) {
  let x = 5;
}
console.log(x); // ReferenceError: y is not defined
```

### 할당되지 않았을 때

- `undeclared` : 선언이 되지 않은 상태
- `undefined` : 선언은 되었지만 초기화 되지 않은 상태 혹은 값이 없는 변수의 값
- `null` : 선언을 하였고, 값을 초기화 하였으나 빈 값을 넣어놓기 원할 때 사용.
- `null` vs `undefined` : 둘의 차이는 `의도성`이다. `null`은 빈 값을 의도적으로 넣어준다.
  ```js
  var b = 125;
  b = null;
  b; // null
  ```
  위와 같이 기존에 있는 값을 지울 때 사용한다.

# 변수 호이스팅

- `호이스팅`이란 JavaScript 변수가 scope 최상단으로 끌어올려지는 것을 의미한다.

```js
console.log(x === undefined); // logs "true"
var x = 3;
```

```js
var myvar = "my value";

(function() {
  console.log(myvar); // undefined
  var myvar = "local value";
})();
```

- `호이스팅`이 일어나도 끌어올려진 변수를 출력하면 여전히 `undefined`를 출력한다.

```js
var x;
console.log(x === undefined); // logs "true"
x = 3;
```

```js
var myVar = "value";
(function() {
  console.log(myVar);
  var myVar = "local valye";
})();
```

- 심지어 이 변수를 사용 혹은 참조한 후에 선언 및 초기화를 하더라도 여전히 `undefined`를 출력한다.

# 함수 호이스팅

- 함수에서는 단지 함수 선언식만 `호이스팅` 된다.

```js
foo(); //bar

function foo() {
  console.log("bar");
}
```

- 함수 표현식은 `호이스팅`이 일어나지 않는다.

```js
foo(); //TypeError: foo is not a function

var foo = function() {
  console.log("bar");
};
```
