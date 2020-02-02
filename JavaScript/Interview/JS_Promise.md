# Promise

---

## What is Promise?

- `promise`는 비동기 처리에 사용되는 객체이다.
- `비동기 처리`란? 특정 코드의 실행이 완료될 때까지 기다리지 않고 다음 코드를 먼저 실행하는 자바스크립트 특성
- `promise`는 주로 서버에서 받아온 데이터를 화면에 표시할 때 사용한다.

## Promise State

- Pending(대기) : 비동기 처리 로직이 아직 완료되지 않은 상태
- Fulfilled(완료) : 비동기 처리가 완료되어 `promise`가 결과값을 반환해준 상태
- Rejected(실패) : 비동기 처리가 실패하거나 오류가 발생한 상태

## Pending(대기)

- `new Promise()` 메서드를 호출하면 `Pending` 상태가 된다.

```js
new Promise();
```

```js
new Promise(function(resolve, reject) {
  // ...
});
```

## Fulfilled(완료)

- 여기서 콜백 함수의 인자가 resolve를 아래와 같이 실행하면 `fulfilled`가 된다.

```js
new Promise(function(resolve, reject) {
  resolve();
});
```

- 그리고 완료 상태가 되면 같이 `then()`를 이용하여 처리 결과 값을 받을 수 있다.

```js
function getData() {
  return new Promise(function(resolve, reject) {
    var date = 100;
    resolve(data);
  });
}

getData().then(function(resolvedData) {
  console.log(resolvedData); //100
});
```

## Rejected(실패)

- `reject`인자로 `reject()`메서드를 실행하면 `Rejeced(실패)` 상태가 된다.

```js
new Promise(function(resolve, reject) {
  reject();
});
```

```js
function getData() {
  return new Promise(function(resolve, reject) {
    reject(new Error("Error"));
  });
}

getData()
  .then()
  .catch(function(error) {
    console.log(error);
  });
```

## 예시

```js
function getData() {
  return new Promise(function(resolve, reject) {
    $.get("url", function(response) {
      if (response) {
        resolved(response);
      }
      reject(new Error("error"));
    });
  });
}

getData()
  .then(function(data) {
    console.log(data);
  })
  .catch(function(error) {
    console.log(error);
  });
```

---

- [더 자세한 예시](https://joshua1988.github.io/web-development/javascript/promise-for-beginners/)
