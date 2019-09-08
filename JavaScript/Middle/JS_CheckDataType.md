# Check Data Type

- 자바스크립트에서 자료형을 확인하는 방법은 다양하다. 그 중에서 사용하는 `typeof`와 `instanceof`로 자료형을 확인해본다.

### Example
```js
const str = '이호수만세';
const strObj = new String('이호수만세');

console.log(typeof str === 'string');       //true
console.log(typeof strObj === 'object');    //true

console.log(str instanceof String);         //false
console.log(strObj instanceof String);      //true
```

```js
const num = 200;
const numObj = new Num(200);

console.log(typeof num === 'number');       //true
console.log(typeof numObj === 'object');    //true

console.log(num instanceof Number);         //false
console.log(numObj instanceof Number);      //true
```

```js
const bool = true;
const boolObj = new Num(true);

console.log(typeof bool === 'boolean');       //true
console.log(typeof boolObj === 'object');    //true

console.log(bool instanceof Boolean);         //false
console.log(boolObj instanceof Boolean);      //true
```

```js
const arr = [10,200,400];
const obj = {a1 : test};

console.log(typeof arr === 'object');       //true
console.log(typeof obj === 'object');    //true

console.log(arr instanceof Array);         //ture
console.log(obj instanceof Object);      //true
```

```js
const empty = null;
const notCalled = undefined;

console.log(typeof empty === 'object');       //true
console.log(typeof notCalled === 'undefined');    //true

console.log(empty instanceof Object);         //false
console.log(notCalled instanceof undefined;      //error
```
- null은 Object를 상속받는 객체가 아니다. `typeof`에서는 자바스크립트언어에서 의도한대로 object를 반환했지만, `instanceof`에서는 false를 반환하여 객체가 아님을 확인할 수 있다.
- `instanceof` 우측에 있는 undefined는 객체가 아니기 때문에 error가 발생한다.
