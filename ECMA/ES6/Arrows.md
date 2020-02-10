# Arrows

## What is Arrows Function?
- Arrows 함수는 `=>`을 사용하는 축약형 함수이다.
- Arrows는 표현식의 결과 값을 반환하는 표현식의 본문 뿐만 아니라 statement block도 지원한다.
- 하지만 일반 함수의 자기 자신을 호출하는 객체를 가리키는 `dynamic this`와 달리 arrows 함수는 코드의 상위 스코프(lexical scope)를 가리키는 `lexical this`를 가리킨다.

#### Example 1
```js
var events = [2,4,6,8];

var odds = events.map( v => v+1);
var nums = events.map ((v,i) => v+i);
var pairs = events.map(v => {event :v, odd : v+1}));

```

#### Code run
```
[3, 5 ,7, 9]
[2, 5, 8, 11]
[{evnet : 2. odd:3},{event :4, odd :5},...]
```

#### Example 2
```js
var bob = {
    _name : "Bob",
    _friends : ["John, Brian"],
    printFriends() {
        this._friends.forEach(f =>
        console.log(this._name + " knows " + f));
    }
}
```

#### Code run
```
Bob knows John
Bob Knows Brian
```

- 위의 예제에서 printFriends() 함수의 서브루틴은 아래와 같이 동작한다.
```js
this._friends.forEach(function (f) {
    console.log(this._name + " knows " + f));
}.bind(this));
```

## Detail the Concept
- arrows function은 일반 function 표현에 비해 구문이 짧고 자신의 `this`, `arguments`, `super` 또는 `new.target`을 바인딩 하지 않는다.

```js
(param1, param2, ..., paramN) => { statements }
(param1, param2, ..., paramN) => expression
//위와 같다. 
=> { return expression}

//매개변수가 없는 함수는 괄호가 필요
() => { statements }

```

```js
// 객체 리터럴 표현을 반환하기 위해서는 함수 본문을 괄호 속에 넣는다.
params => ({foo : bar})

// 매개변수 목록 내에 비구조화도 지원된다.
var f = ([a,b] = [1,2], {x:c}={x:a+b}) => a + b + c;
f(); //6

```

## 짧아지는 효과
```js
var materials = [
  'Hydrogen',
  'Helium',
  'Lithium',
  'Beryllium'
];
```

```js
materials.map(function(material) { 
  return material.length; 
}); // [8, 6, 7, 9]
```

```js
materials.map((material) => {
  return material.length;
}); // [8, 6, 7, 9]
```

```js
materials.map(({length}) => length); // [8, 6, 7, 9]
```

## not binding `this`
- arrows 함수전까지는, 모든 새로운 함수는 자신의 `this` 값을 정의했다. 이는 객체지향 스타일로 프로그래밍할 때 별로 좋지않다.


```js
function Person() {
    var that = this;
    that.age = 0;

    setInterval(function growUp(){
        that.age++;
    },1000);
}

var p = new Person();
```

```js
function Person(){
    this.age = 0;

    setInterval(() => {
        this.age++;
    },1000);
}

var p = new Person();
```

- 화살표 함수는 전역 context에서 실행될때 `this`를 새로 정의하지 않는다.
- 대신 code에서 바로 바깥의 함수의 `this`값이 사용된다.
- 즉, `this`를 `clouser` 값으로 처리하는 것과 같다.
- 따라서 `setInterval`에 전달된 함수의 `this`는 `setInterval`을 포함한 function의 `this`와 동일하다.
