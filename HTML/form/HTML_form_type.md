# Input Form type

- 다양한 type의 input 요소를 포함 할 수 있다.
- HTML에서 자주 사용되는 Input element의 대표적인 타입은 아래와 같다.

    1. text
    2. password
    3. submit
    4. reset
    5. image
    6. radio
    7. button
    8. checkbox
    9. file
<br>

- HTML5에서 새롭게 추가된 Input element type은 아래와 같다.
    1. number
    2. range
    3. color
    4. date
    5. time
    6. datatime-local
    7. month
    8. week
    9. email
    10. url
    11. tel
    12. search

## "text"
- 사용자로부터 한 줄의 text를 입력 받을 수 있다.

```html
<form>
  제목 : <input type="text" name="title">
</form>
```
<form>
  제목 : <input type="text" name="title">
</form>

## "password"
- 사용자로부터 비밀번호를 입력 받을 수 있다.
```html
<form action="/">
  사용자명 : <input type="text" name="username"><br/>
  <input type="submit" value="전송">
</form>
```
<form action="/">
  사용자명 : <input type="text" name="username"><br/>
  <input type="submit" value="전송">
</form>

## "submit"
- 사용자로부터 입력 받은 data를 서버의 form-handler로 제출하는 버튼이 된다.
- form-handler란 입력 받은 데이터를 처리하기 위한 서버측의 웹 페이지를 의미한다.

```html
<form action="/">
  사용자명 : <input type="text" name="username"><br/>
  <input type="submit" value="전송">
</form>
```
<br>
<form action="/">
  사용자명 : <input type="text" name="username"><br/>
  <input type="submit" value="전송">
</form>

## "reset"
- 사용자가 입력한 값이 초기 값으로 재설정하는 버튼이 된다.
```html
<form action="/">
  사용자명 : <input type="text" name="username" value="개발곰"><br/>
  <input type="reset" value="재설정">
</form>
```
<br>
<form action="/">
  사용자명 : <input type="text" name="username" value="개발곰"><br/>
  <input type="reset" value="재설정">
</form>

## "image"
- 전송버튼 (submit button)의 역할을 하면서 이미지로 출력되는 버튼이 있다.
```html
<form action="/">
  사용자명 : <input type="text" name="username"><br/>
  <input type="image" src="/resources/images/logo/64x64.png">
</form>
```
- 전송 버튼이 아닌 일반적인 버튼을 이미지로 처리하려면 `<img>` tag를 사용하고 js를 이용하여 action을 지정해야한다.

## "button"
- 일반적인 button이 생성된다.
- button은 `<button>` 태그로도 표현이 가능하다.

```html
<input type="button" onclick="alert('Hello World!')" value="Click Me!">
```
<input type="button" onclick="alert('Hello World!')" value="Click Me!">

## "radio"
- 사용자로부터 여러 개의 option중에서 단 하나의 option만을 입력받을 수 있다.
- 이때 서버로 정확한 입력을 전송하기 위해서는 모든 input 요소의 name 속성이 같아야 한다.

```html
<input type="radio" name="fruit" value="apple" checked> 사과
<input type="radio" name="fruit" value="banana"> 바나나
<input type="radio" name="fruit" value="orange"> 오렌지
<input type="radio" name="fruit" value="strawberry"> 딸기
```
<input type="radio" name="fruit" value="apple" checked> 사과
<input type="radio" name="fruit" value="banana"> 바나나
<input type="radio" name="fruit" value="orange"> 오렌지
<input type="radio" name="fruit" value="strawberry"> 딸기

## "checkbox"
- 사용자로부터 여러 개의 옵션 중에서 다수의 옵션을 입력 받을 수 있다.
- checkbox는 radio button과 달리 여러 개의 옵션을 한 번에 받을 수 있다.
- 이때 서버로 정확한 입력을 전송하기 위해서는 모든 input 요소의 name 속성이 같아야 한다.

```html
<input type="checkbox" name="fruit" value="apple" checked> 사과
<input type="checkbox" name="fruit" value="banana"> 바나나
<input type="checkbox" name="fruit" value="orange"> 오렌지
<input type="checkbox" name="fruit" value="strawberry"> 딸기
```
<input type="checkbox" name="fruit" value="apple" checked> 사과
<input type="checkbox" name="fruit" value="banana"> 바나나
<input type="checkbox" name="fruit" value="orange"> 오렌지
<input type="checkbox" name="fruit" value="strawberry"> 딸기

## "file"
- 파일을 전송할 수 있다.

```html
<input type="file" name="imageFile" accept="image/*">
```

<input type="file" name="imageFile" accept="image/*">


## "number"
- input element는 사용자가 숫자를 입력할 수 있도록 해준다.
- 일반 text 타입과 다른 점은 입력 필드 우측에 숫자의 크기를 조절할 수 있는 상하 버튼이 생긴다는 점이다.
- 브라우저의 지원 여부에 따라 min 속성과 max 속성을 이용하여 숫자 선택에 제한을 설정할 수 있다.
- 익스 플로어 9와 그 이전 버전에선 지원하지 않는다.

```html
<input type="number" name="num" min="1" max="9">
```

<input type="number" name="num" min="1" max="9">

## "range"
- input 요소는 사용자가 일정 범위 안의 값만을 입력할 수 있도록 해준다.
- 브라우저 지원 여부에 따라 값을 선택하기 위한 수평 조절바를 보여준다.
- 익스 플로어 9와 그 이전 버전에선 지원하지 않는다.

```html
0 <input type="range" name="favnum" min="1" max="9"> 9
```

0 <input type="range" name="favnum" min="1" max="9"> 9

## "color"
- input 요소는 사용자가 색상을 입력 할 수 있도록 한다.
- 선택된 색상은 #을 제외한 6자리의 16진수 색상값으로 전송된다.
- 브라우저 지원 여부에 따라 색상을 선택하기 위한 도구를 보여준다.
- 사파리 9.1과 그 이전 버전, 익스플로어 11과 그 이전 버전에서 지원하지 않는다.

```html
<input type="color" name="color" value="#FF0000">
```

<input type="color" name="color" value="#FF0000">

## "date"
- 사용자가 날짜를 입력할 수 있게 해준다.
- 브라우저의 지원 여부에 따라 날짜를 선택하기 위한 캘린더를 보여준다.
- min과 max 속성을 사용하여 날짜 선택에 제한을 설정할 수 있다.
- 파이어폭스, 익스플로어 11과 그 이전 버전에서는 지원하지 않는다.

```html
<input type="date" name="day2" min="1977-01-01" max="2020-12-31">
```

<input type="date" name="day2" min="1977-01-01" max="2020-12-31">


## "time"
- 사용자가 시간을 입력 할 수 있도록 해준다.
- 브라우저의 지원 여부에 따라 시간을 선택하기 위한 도구를 보여준다.
- 파이어폭스, 익스플로어 12와 그 이전 버전에서는 지원하지 않는다.

```html
<input type="time" name="time">
```

<input type="time" name="time">

## "email"
- 사용자가 email 주소를 입력 할 수 있도록 해준다.
- 브라우저의 지원 여부에 따라 전송할 때 입력한 email 주소가 유효한 email 주소인지 자동으로 검사한다.

```html
<input type="email" name="email">
```

<input type="email" name="email">


---
이외에도 "search", "tel", "url" 등이 있지만 생략한다.

