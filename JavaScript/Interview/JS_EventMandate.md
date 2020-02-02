# 이벤트 위임

---

> 이벤트 위임이란 다수의 자식 요소에 각각 이벤트 헨들러를 바인딩하는 대신 하나의 부모요소에 이벤트 핸들러를 적용하는 방식

- 어플리케이션을 제작할 때 사용자가 페이지 요소를 조작할 수 있도록 페이지의 버튼, 텍스트, 이미지등에 이벤트를 붙여야 할 때가 있다.

##### 예시

```js
<ul id="todo-app">
  <li class="item">Walk the dog</li>
  <li class="item">Pay bills</li>
  <li class="item">Make dinner</li>
  <li class="item">Code for one hour</li>
</ul>
```

##### Event Listener setting

```js
document.addEventListener("DOMContentLoaded", function() {
  let app = document.getElementById("todo-app");
  let items = app.getElementsByClassName("item");

  // 각 아이템에 이벤트 리스너를 등록합니다.
  for (let item of items) {
    item.addEventListener("click", function() {
      alert("you clicked on item: " + item.innerHTML);
    });
  }
});
```

- 위와 같은 `event listener` 등록은 요소의 수가 적을때는 효율적이고 잘 돌아가지만, 요소의 갯수가 10,000개 라면 매우 비효율적이다.
- 즉, 면접관에세 먼저 요소의 갯수를 물어보고 10개 미만이라면 위와 같이 이벤트를 걸어주는게 좋다.

<br />

- item 갯수마다 `event listener`를 생성, 등록하는 것보다 모든 list에 대해서 한 개의 `event listener`를 생성하여 전체를 등록하는 것이 효율적이다.
- 즉, 전체 아이템에 `event listener`에 이벤트를 설정하게 되면 사용자가 한 개를 선택했을 때 `event listener`가 해당 아이템에 대해서 이벤트를 발생시킨다.
- 이것이 `이벤트 위임`이다.

```js
document.addEventListener("DOMContentLoaded", function() {
  let app = document.getElementById("todo-app");

  // 리스트 아이템의 전체 영역에 이벤트 리스너를 등록한다.
  app.addEventListener("click", function(e) {
    if (e.target && e.target.nodeName === "LI") {
      let item = e.target;
      alert("you clicked on item: " + item.innerHTML);
    }
  });
});
```
