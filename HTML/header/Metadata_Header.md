# 🎁 Metadata : the <meta> element

---
- 메타 데이터는 데이터를 설명하는 데이터이다. 
---

```HTML
<meta charset="utf-8">
```
- 위의 요소는 `utf-8` character set을 포함하는 metadata 형식이다.

```html
<meta name="author" content="Chris Mills">
<meta name="description" content="The MDN Learning Area aims to provide
complete beginners to the Web with all they need to know to get
started with developing web sites and applications.">
```
- `name`은 어떤 타입의 정보를 가지고 있는지 메타 요소의 형태를 알려준다.
- `content`는 실제 메타데이터의 컨첸츠이다.
- `name`에 `author`을 지정하는 것은 contents 작성자에 대한 정보를 볼 수 있게 해준다. 이렇게 해주면 검색엔진에서 표출 될 수 있다.

```html
<meta name="twitter:title" content="Mozilla Developer Network">
```
- 위의 코드는 Twitter의 유사한 형태의 metadata인데, 특정 웹사이트의 url이 twitter.com에 표시될때와 유사한 효과가 있다.


