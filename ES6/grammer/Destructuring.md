# Destructuring

- Destructuring는 배열과 객체에 패턴 매칭을 통한 바인딩을 제공한다.
- Destructuring는 할당 실패에 유연하며, 실패시 `undefined` 값이 자동 할당 된다.


### Example

```js
var [a, ,b] = [1,2,3];

var { op : a, lhs : {op : b}, rhs : c} = getASTNode()

var { op, lhs, rhs} = getASTNode()

function g({name : x}) {
    console.log(x);
}
//g({name : 5})

var [a] = [];
//a === undefined;

var [a = 1] = [];
//a === 1;
```

