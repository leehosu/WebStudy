# Transfer to Data Type

## parseInt
- `parseInt()`는 어떤 내장함수 객체에도 속하지 않은, 전역에서 사용할 수 있는 내장 함수이다. 
- `parseInt()`를 활용하여 문자열 자료형을 숫자로 변환할 수 있다. 
- `parseInt()`는 두 개의 인자를 받는데, 첫 번째 인자에는 숫자로 변환하고 싶은 값을 넣고, 두 번째 인자는 특정 진수를 나타내는 정수값을 넣는다.
```
parseInf(값, 진수);
```

### Example
```js
console.log(parseInt('15'));        //15
console.log(parseInt('15',10));     //15
console.log(parseInt('15',2));      //1
console.log(parseInt(5.15));        //5
console.log(parseInt('5.15'));      5
```

## parseFloat
- `parseFloat` 함수는 대입된 값을 부동 소수점 숫자로 변환한다. 만일 값에 숫자, 소수점, 지수, 기호가 아닌 값이 들어오는 경우 생략된다.
```
parseFloat(값);
```

### Example
```js
console.log(parseFloat(5.55));              //5.55
console.log(parseFloat('5.55'));            //5.55
console.log(parseFloat('5.55의 결과값 '));   //5.55
```
- 숫자 5.55을 넣으면 소수점이 있는 실수이기 때문에 그대로 값을 반환하고 문자 5.55를 넣으면 소수점이 있는 숫자형으로 변환하여 반환한다. 또, 문자 5.55이외에 다른 문자 또는 공백을 넣으면 숫자 5.55만 남기고 생략되어 반환된다.
