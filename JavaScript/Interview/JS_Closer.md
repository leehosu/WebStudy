# 루프에서 클로져 이용하기

---

## Closer?

- 클로져는 내부함수가 `scope`밖에 있는 변수에 접근하는 것이다.

#### Q. 정수 값을 갖는 리스트를 반복문으로 접근하여 해당 요소를 3초를 지연시키고 값을 출력하라.

##### 잘못된 code

```js
const arr = [10, 12, 15, 21];
for (var i = 0; i < arr.length; i++) {
  setTimeout(function() {
    console.log("The index of this number is: " + i);
  }, 3000);
}
```

- 위와 같은 코드는 3초마다 0,1,2,3이 출력되는 것이 아니라 모두 4가 출력된다.

- 문제의 원인은 `serTimeout`함수가 `i`를 반복하는 `scope` 밖의 `scope`를 갖는 `closer`를 생성하기 때문이다.
- 즉, 그렇기 때문에 3초가 흐른 후 `closer`가 실행되고 `i` 값을 출력할 때 반복문의 종료값인 `4`가 출력된다.

##### Answer 1

```js
const arr = [10, 12, 15, 21];
for (var i = 0; i < arr.length; i++) {
  setTimeout(
    (function(i_local) {
      return function() {
        console.log("The index of this number is: " + i_local);
      };
    })(i),
    3000
  );
}
```

- 위의 방법은 i값을 `setTimeout`함수의 인수로 취급하여 각 호출마다 올바른 값에 접근을 하게 만드는 방법이다.

##### Answer 2

```js
const arr = [10, 12, 15, 21];
for (let i = 0; i < arr.length; i++) {
  setTimeout(function() {
    console.log("The index of this number is: " + i);
  }, 3000);
}
```

- 위의 방법은 변수를 `var`가 아닌 `let`으로 할당하여 함수가 호출 될 때 마다 `i`값이 바인딩되는 `es6`문법을 사용하는 방법이다.
