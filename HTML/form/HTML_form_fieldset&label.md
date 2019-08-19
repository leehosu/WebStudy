# HTML Form Fieldset & label

## fieldset element
- form element와 관련된 데이터들을 하나로 묶어주는 역할을 한다.
- legend element는 fieldset element 안에서만 사용할 수 있으며, 제목을 표시한다.

```html
<form>
  <fieldset>
    <legend>로그인 인증</legend>
    <p>사용자명 : <input type="text" name="username"></p>
    <p>비밀번호 : <input type="password" name="password"></p>
    <button type="button">로그인</button>
  </fieldset>
</form>
```
<form>
  <fieldset>
    <legend>로그인 인증</legend>
    <p>사용자명 : <input type="text" name="username"></p>
    <p>비밀번호 : <input type="password" name="password"></p>
    <button type="button">로그인</button>
  </fieldset>
</form>

## Label Element
- label element는 사용자가 input text, checkbox, radio button 등을 좀더 쉽게 선택 할 수 있도록 도와준다.
- label 요소를 클릭하면 input text의 경우에는 자동으로 focus가 이동하고 checkbox, radio button의 경우는 자동으로 선택된다.
- label의 for 속성의 이름과 form 요소의 id 값이 일치해야한다.

```html
<label for="html">HTML</label> <input type="checkbox" name="html" id="html">
<label for="css">CSS</label> <input type="checkbox" name="css" id="css">
```

<label for="html">HTML</label> <input type="checkbox" name="html" id="html">
<label for="css">CSS</label> <input type="checkbox" name="css" id="css">

