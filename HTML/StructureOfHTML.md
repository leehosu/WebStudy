# 🚀 Structure of HTML Element
<br>

![tagElement](../image/html/tagElement.png)

- element의 주요 부분은 다음과 같다.

1. 여는 태그 (Opening tag) : 요소의 이름(`p`,`div` 등), 열고 닫는 꺽쇠 괄호(`<`)로 구성된다. 요소가 시작부터 효과가 적용된다.

2. 닫는 태그 (Closing tag) : 요소의 이름 앞에 슬래시(`/`)가 있는 것을 제외하면 여는 태그와 같다. 요소의 끝에 위치하며 닫는 태그를 적어주지 않으면 오류가 발생한다.

3. 내용 (Content) : 요소의 내용이다.

4. 요소(Element) : 여는 태그, 닫는 태그, 내용을 통틀어 요소라고 한다.

---

## Nesting element 
- 포함된 element로, element안에 다른 element가 들어갈 수 있다.

```
<p> My Name is Lee <strong> hosu </strong>. </p>
```
- 실행결과 : <p> My Name is Lee <strong> hosu </strong>. </p>
<br>

- 위의 예제에서는 `p`요소가 먼저 열렸고 그리고 `strong`요소가 열렸다 그렇게 때문에 닫을때도 `strong`먼저 닫아주고 `p`요소를 닫아줘야한다.

---

## Block Level Element VS Inline Element

- HTM에는 두 가지 종류의 element가 있다.

### block level element
- 웹 페이지 상에 Block을 만드는 element이다. 
- Block level element는 앞뒤 요소 사이에 새로운 line을 만들고 나타낸다.
- 즉, Block level element 이전과 이후 요소 사이의 줄을 바꾼다.
- 일반적으로 페이지의 구조적 요소를 나타낼 때 사용된다.
- 예를 들어, 개발자는 Block level element를 사용하여 단락(Paragraphs), 목록(lists), 네비게이션 메뉴(Navigation Menus), 꼬리말(Footers)등을 표현할 수 있다.
- Block Level Element는 Inline Element요소에 중첩될 수 없다.

### Inline Element
- Inline Element는 항상 Block Level Element내에 포함되어 있다.
- 문서의 한 단락같은 큰 범위에는 적용될 수 없고 문장, 단어 같은 같은 부분에만 적용될 수 있다.
- 새로운 line을 만들어내지 않는다.
- 즉, Inline element를 작성하면 그것을 작성한 단락내에 나타나게 된다.
- 예를들어, 하이퍼링크를 정의하는 요소인 `<a>`, text를 강조하는 요소인 `<em>`, `<strong>`등이 있다.

### Example
```html
<em>first</em><em>second</em><em>third</em>

<p>fourth</p><p>fifth</p><p>sixth</p>
```

- 실행 결과

<em>first</em><em>second</em><em>third</em>

<p>fourth</p><p>fifth</p><p>sixth</p>

---

## Empty Elements
- 모든 요소가 위에 언급된 여는 태그, 내용, 닫는 태그 패턴을 따르는건 아니다.
- 주로 문서에 무언가를 첨부하기 위해 단일 태그 (single tag)를 사용하는 요소도 있다.

### Example
```html
<img src="https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png">
```
- 실행 결과 
<img src="https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png">

