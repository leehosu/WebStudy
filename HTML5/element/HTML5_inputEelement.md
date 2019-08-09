# 🚚 HTML input element

- HTML5에서 새롭게 추가된 input element는 아래와 같다.
    1. datalist element
    2. keygen element
    3. output element


## datalist element
- datalist element는 input element에 대해 미리 정의된 옵션 리스트를 명시해주는 element이다
- 사용자는 text를 바로 입력해도되고, dropdown 메뉴에서 미리 정의한 옵션 중에서 선택해도 된다.
- input element의 list 속성값이 datalist element의 id 값과 반드시 일치해야한다.

```html
<input list="lectures" name="lecture">
     <datalist id="lectures">
        <option value="HTML">
        <option value="CSS">
        <option value="JAVA">
        <option value="C++">
     </datalist>
<input type="submit" value="전송">

```
[실행 결과 ](http://tcpschool.com/examples/tryit/tryhtml.php?filename=html5_element_input_01)

## keygen element
- keygen element의 목적은 사용자가 인증할 수 있는 안전한 방법을 제공하는 것이다.
- keygen element는 사용자가 입력한 데이터를 암호화하여 서버로 전송한다.
- 이때 생성된 key를 가지고 서버는 해당 사용자의 인증을 수행한다.

```html
<form action="/examples/media/request.php">
    사용자 : <br>
    <input type="text" name="username"><br>
    암호화방법 : <br>
    <keygen name="security"><br>
</form>
```

[실행 결과](http://tcpschool.com/examples/tryit/tryhtml.php?filename=html5_element_input_02)

## output element
- output element는 script 등으로 실행된 계산의 결과를 바로 표시해주는 element이다.

```html
<form action="/examples/media/request.php"
    oninput="total.value=parseInt(value01.value)/parseInt(value02.value)">
    <input type="number" id="value01" name="input01" value="20">
    /
    ( 0
    <input type="range" id="value02" name="input02" value="50" min="0" max="100">
    100 )
    =
    <output name="total" for="value01 value02">
    </output><br><br>
</form>
```