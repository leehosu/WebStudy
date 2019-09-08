# Truncate String

---
- 긴 문장에서 원하는 위치의 특정 문자열만 잘라내는 것이 필요한 경우가 있다.
- 자바스크립트 내장 함수중에 문자열 자르는 여러 함수가 있지만 그 중에 가장 많이 쓰이고 유용한 `slice`,`substring`,`substr`에 대해 공부한다.
---

## slice()

- String 내장 객체의 `slice` 메소드는 인자로 시작 지점의 인덱스와 종료 지점의 인덱스를 받는다. 두 번째 인자인 종료 인덱스는 선택 사항이므로 필수값은 아니다.
- 지정한 범위의 인덱스 문자열을 반환하되, 기존 문자열에 영향을 미치지 않는다.
```
'문자열'.slice(시작 인덱스, 종료 인덱스)
```

### Example

```js
const sentence = 'The sum will shine on us again';

console.log(sentence.slice(13));        //shine on us again
console.log(sentence.slice(13,24));     //shine on us
console.log(sentence.slice(0));         //the sun will shine on us again
console.log(sentence.slice(0,-23));     //The sun
console.log(sentence.slice(50));        // 수행되지 않는다.
console.log(sentence.slice(7,2));       // 수행되지 않는다.
```

## subString()
- String 내장 객체의 `substring` 메소드는 인자로 시작 지점의 인데스와 종료 지점의 인덱스를 받는다.
- 역시 두 번째 인자인 종료 인덱스는 선택 사항이므로 필수값은 아니다.
- `substring` 메소드의 실행 결과 값은 새로운 문자열을 반환하며 기존 문자열을 변경하지 않는다.

```
'문자열'.substring(시작 인덱스, 종료 인덱스)
```

### Example
```js
const sentence = 'this will be the end of wakanda';

console.log(setence.substring(13));         //the end of wakanda
console.log(setence.substring(13,20));      //the end
console.log(setence.substring(0));          //this will~~
console.log(setence.substring(0,-20));      // 음수를 넣으면 수행되지 않는다.
console.log(setence.substring(50));         //문자열 길이를 뛰어넘으면 빈 값을 반환한다.
console.log(setence.substring(20,13));      //첫번째 인자가 두번째 인자보다 클 경우 두 개의 인수를 바꿔서 출력한다. 즉 (13,20)으로 출력된다.
```

## substr()
- String의 내장 객체인 `substr` 메소드는 인자로 시작 지점의 인덱스와 길이를 받는다. 두 번째 인자인 종료 인덱스는 선택 사항이므로 필수값은 아니다.
- 지정된 인덱스로부터 시작해서 지정된 문자 수 또는 길이만큼의 새 문자열을 반환한다.
- 즉, 추출하고자 하는 문자열의 길이를 정확히 알고 있는 경우에 `substr` 메소드를 활용 하는 것이 좋다.

### Example
```js
const sentence = 'Wakanda Forever!!!';

console.log(sentence.substr(8));        //Forever!!!
console.log(sentence.substr(8,7));      //Forever
console.log(sentence.substr(0));        //Wakande Forever!!!
console.log(sentence.substr(-10));      //Forever!!!
console.log(sentence.substr(0,-3));     //
console.log(sentence.substr(30));       //
console.log(sentence.substr(0,30));     //Wakanda Forever!!!
```
- 첫 번째 인자에 음수를 넣으면 문자열의 뒤에서부터 위치를 결정한다.
- `substr` 함수의 두 번째 인자에 음수를 넣으면 정상적으로 실행되지 않는다.
- 문자열의 길이보다 큰 수를 첫 번째 인자에 대입하면 해당하는 인덱스를 찾지 못하기 때문에 빈 값을 반환한다.
- 두 번째 인자가 문자열의 길이 보다 크다면 전체 다 출력한다.
