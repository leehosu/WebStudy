# Form Input Attribute

## input element Attribute
- input요소는 다양한 속성을 가지고 있다.
- input 요소의 여러 속성을 사용하면 사용자가 입력하는 방식을 더욱 다양하게 제어할 수 있다.
- HTML에서 자주 사용되는 input element attribute는 아래와 같다.
    1. value
    2. readonly
    3. disabled
    4. maxlenght
    5. size

## value
- input element의 입력 필드에 표시되는 초깃값을 설정한다.
```html
사용자명: <input type="text" name="name" value="이호수">
```

사용자명: <input type="text" name="name" value="이호수">

## readonly
- 사용자가 입력 필드를 볼 수는 있으나, 수정할 수 없도록 설정한다.
- disabled 속성과 다른 점은 submit 버튼을 누르면 값이 서버로 전송된다는 점이다.

```html
사용자명: <input type="text" name="name" value="이호수" readonly>
```
사용자명: <input type="text" name="name" value="이호수" readonly>

## disabled 
- 사용자가 입력필드에 아예 사용할 수 없도록 설정한다.

```html
사용자명: <input type="text" name="name" value="이호수" disabled>
```

사용자명: <input type="text" name="name" value="이호수" disabled>

## maxlength
- 입력 필드에 입력 할 수 있는 최대 문자수를 설정한다.

```html
사용자명: <input type="text" name="name" value="이호수" maxlength="10">
```

사용자명: <input type="text" name="name" value="이호수" maxlength="10">

## size
- 입력 필드에 보여지는 input element의 크기를 설정한다.
- maxlength와 달리 입력 필드가 한 번에 보여줄 수 있는 문자수 만을 의미한다.

```html
사용자명: <input type="text" name="name" value="이호수" size="10">
```

사용자명: <input type="text" name="name" value="이호수" size="10">
