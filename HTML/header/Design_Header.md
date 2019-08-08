# 🎨 CSS , JS In Header

---
- 현대의 모든 웹사이트는 상호작용 기능이 많은 영상 플레이어, 지도, 게임등을 위해 JavaScript가 필요하고, 이것들을 더 멋져 보이게 하기 위해 CSS가 사용된다.
- `<link>`, `<script>` 요소를 사용하여 웹 페이지에 적용된다.
---

```html
<link rel="stylesheet" href="my-css-file.css">
```
- head에 위치하며, `rel="stylesheet"` - 문서의 style sheet임을 타나냄과 동시에 css 파일의 경로를 포함하는 href를 내장한다.

```html
<script src="my-js-file.js"></script>
```
- `<script>`는 head에 들어갈 필요가 없다.
- `</body>` 태그 바로 앞, 문서 본문의 맨 끝에 넣는것이 좋으며 JavaScript를 적용하기 전에 모든 HTML 내용을 브라우저가 읽은 후 적용하는 것이 좋다.
