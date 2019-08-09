# 🚗 HTML5의 문서의 기본구조

## HTML5 개요
- HTML5에서의 DOCTYPE 선언이 매우 간단해졌다.

```HTML
<!DOCTYPE html>
```

- 또한 character set의 선언도 매우 간단해졌다.


```html
<!-- HTML5 이전 -->
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">

<!-- HTML5 -->
<meta charset="UTF-8">
```

## HTML5 변경사항

#### HTML5에서 추가된 요소 및 타입
- 의미(semantic) 요소 : `<header>`, `<nav>`, `<main>`, `<section>`, `<aside>`, `<article>`, `<footer>`, `<figure>`
- 멀티 미디어 요소 : `<video>`, `<audio>`
- 그래픽 요소 : `<canvus>`,`<svg>`
- input 요소의 타입 : number, date, time, calendar,range 등

#### HTML5 에서 추가된 JavaScript API
- Geolocation
- Drag and Drop
- Web Storage
- Application Cache
- Web Worker
- Server Sent Events

#### HTML5에서 추가된 semantic element
- `<header>` : HTML 문서나 section 부분에 대한 header를 정의함.
- `<nav>` : HTML 문서 사이를 탐색할 수 있는 link의 집합을 정의함.
- `<main>` : HTML 문서의 주요 content를 정의함.
- `<section>` : HTML 문서에서 section 부분을 정의함.
- `<article>` : HTML 문서에서 독립적인 하나의 article 부분을 정의함.
- `<aside>` : HTML 문서에서 페이지 부분 이외의 content 를 정의함.
- `<footer>` : HTML 문서나 section 부분에 대한 footer를 정의함.

