# 디바운싱
---

- 브라우저 이벤트에는 윈도우 크기를 재조정하거나 페이지 스크롤을 내리는 등의 매우 짧은 시간에 다수 발생되는 이벤트가 있다.
- 어플리케이션 제작에 관해 논할 때, 스크롤링 이나 화면 재조정, 키눌림과 같은 이벤트를 꼭 짚고 넘어가야한다.

- `Debouncing`은 실제로 함수가 다시 호출되기 전까지 시간 간격을 두어 성능 이슈를 해결하는 방법이다.

```js
// 이벤트를 감쌀 디바운싱 함수
  function debounce(fn, delay) {
    // 타이머 선언
    let timer = null;
    // 타이머 변수에 접근 가능한 클로져 함수
    return function() {
      // 클로져 함수 안에서 this 와 arguments 변수로 디바운싱 함수의 스코프와 변수를 접근한다.
      let context = this;
      let args = arguments;
      // 만약 이벤트가 호출되면 타이머를 초기화 하고 다시 시작한다.
      clearTimeout(timer);
      timer = setTimeout(function() {
        fn.apply(context, args);
      }, delay);
    }
  }
```

- 실제로 위 함수를 사용하는 부분은 아래와 같다.
```js
 // 사용자가 스크롤 할 때 호출되는 이벤트 함수
  function foo() {
    console.log('You are scrolling!');
  }

  // 이벤트 함수를 디바운싱 함수로 감싸서 2초 마다 발생하도록 한다.
  let elem = document.getElementById('container');
  elem.addEventListener('scroll', debounce(foo, 2000));
``` 