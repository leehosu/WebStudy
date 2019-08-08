# 🌡 Attribute of HTML

![AttributeHTML](../../image/html/AttributeHTML.png)

- 요소는 위의 이미지와 같이 속성을 가질 수 있다.
- 속성은 요소에 실제론 나타내고 싶지 않지만 추가적인 내용을 담고 싶을때 사용한다.
- 위에는 나중에 스타일에 관련된 내용이나 기타 내용을 위해 해당 요소를 구분할 수 있는 `class` 속성을 추가했다.

- 속성을 사용할 때에는 아래 내용을 지켜야한다.
    1. 요소 이름 다음에 바로 오는 속성은 요소 이름과 속성 사이에 공백이 있어야 되고, 하나 이상의 속성들이 있는 경우엔 속성 사이에 공백이 있어야 한다.
    2. 속성 이름 다음엔 등호(`=`)가 있어야 한다.
    3. 속성 값은 열고 닫는 따옴표로 감싸야 한다.

---

## 요소에 속성 추가하기
- `href` : 연결하고자 하는 웹 주소를 지정한다.
- `title` : 링크에 대한 추가 정보를 나타낸다. 이 내용은 링크 위로 마우스를 옮겼을 때 나타난다.
- `target` : 링크가 어떻게 열릴지 지정한다. 예를들어 `target = "_blank" `는 새탭에서 링크를 연다.

### Example
```html
<p>
    A link to my 
    <a href="https://www.mozilla.org/" title="The Mozilla homepage" target="_blank">favorite website
    </a>
</p>
```

- 실행 결과 : 
<p>
    A link to my 
    <a href="https://www.mozilla.org/" title="The Mozilla homepage" target="_blank">favorite website
    </a>
</p>

---

## Boolean Attributes
- 값이 없는 속성을 볼 수 있는데 이를 Boolean 속성이라고 하며 일반적으로 그 속성의 이름과 동일한 하나의 값만을 가질 수 있다.

### Example
- `disabled` 속성을 `input` 요소에 할당하면 사용자가 데이터를 입력 할 수 없도록 비활성화 할 수 있다. 

```html
<input type="text" disabled>

<input type="text">
```
- 실행 결과 : 
<input type="text" disabled> <input type="text">

---

## 속성값의 따옴표 생략
- 웹을 둘러보면 따옴표가 없는 속성값을 포함한 Markup을 볼 수 있다.
- 어떤 상황에서는 허용되지만, 다른 상황에서는 오류를 야기한다.

- 기존에 우리는 `href` 속성만 있는 기본적인 버전을 작성했다.

```html
<a href=https://www.mozilla.org/>favourite website</a>
```

- 하지만 여기에 `title` 속성을 추가하면 문제가 발생한다.

```html
<a href=https://www.mozilla.org/ title=The Mozilla homepage>favorite website</a>
```

- 브라우저는 `title`이 3개의 속성을 가진다고 생각할 것 이다.
- `title` 속성값 'The'와 두개의 boolean 속성값 'Mozilla','homepage'로 생각할 것이다.

### 큰 따옴표, 작은 따옴표
- HTML에서 큰 따옴표, 작은 따옴표는 개발자의 스타일 문제로 원하는 것을 쓰면 된다.
- **하지만 두 가지를 섞어 쓰면 안된다.**

---