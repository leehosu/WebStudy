# ✏ HTML text funamental

---
- HTML의 주요 작업 중 하나는 브라우저가 text를 올바르게 표시 할 수 있도록 텍스트 구조와 의미를 제공하는 것이다.
---

## Title and Paragraph
- 대부분의 구조화된 text는 기사, 신문, 대학 교과서, 잡지 등 무엇을 읽든지 간에 제목과 단락으로 구성된다.

```html
<p> My name is Lee hosu, oh yes I am.</p>
```
- HTML에서 각 단락은 `<p>` 요소 안에 둘러 싸여 있어야한다.

##### heading
- heading 요소는 `<h1>`,`<h2>`,`<h3>`,`<h4>`,`<h5>`,`<h6>`로 총 6개가 있다.
- 각 요소는 문서에서 다른 수준의 내용을 나타낸다.
주로 main title을 `<h1>`으로 나타내고 소제목을 `<h2>`등 수준을 다르게 해서 사용한다.

### 구조화된 계층 구현
```html
<h1>The Crushing Bore</h1>

<p>By Chris Mills</p>

<h2>Chapter 1: The dark night</h2>

<p>It was a dark night. Somewhere, an owl hooted. The rain lashed down on the ...</p>

<h2>Chapter 2: The eternal silence</h2>

<p>Our protagonist could not so much as a whisper out of the shadowy figure ...</p>

<h3>The specter speaks</h3>

<p>Several more hours had passed, when all of a sudden the specter sat bolt upright and exclaimed, "Please have mercy on my soul!"</p>
```
<h1>The Crushing Bore</h1>

<p>By Chris Mills</p>

<h2>Chapter 1: The dark night</h2>

<p>It was a dark night. Somewhere, an owl hooted. The rain lashed down on the ...</p>

<h2>Chapter 2: The eternal silence</h2>

<p>Our protagonist could not so much as a whisper out of the shadowy figure ...</p>

<h3>The specter speaks</h3>

<p>Several more hours had passed, when all of a sudden the specter sat bolt upright and exclaimed, "Please have mercy on my soul!"</p>


- `<h1>` 요소는 최상위에 있는 표제이며 나머지 다른 표제들은 계층적으로 이 요소 밑에 위치하므로 가급적이면 페이지당 하나의 `<h1>` 요소를 사용해야한다.
