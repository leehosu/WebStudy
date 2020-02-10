# Default + Reset + Spread

- 파라미터에 기본 값을 설정 할 수 있다.

```js
function f(x, y = 12){
    return x + y;
}
f(3) // 15
```

- 가변인자를 사용가능하며, 배열로 치환 시켜 준다.
- Rest Parameters는 arguments보다 직관성을 제공한다.

```js
function f( x, ...y){
    // y는 Array ["hello", true]
    return x * y.lenght;
}

f(3, "hello", true)
// 6 
```

- 함수 호출 시 배열을 일련의 인자에 나누어 주입한다.

```js
function f(x,y,z){
    return x + y + z;
}

f(...[1,2,3])
//6
```
