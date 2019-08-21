# Template

- Template literals은 문법적으로 더 편하게 string을 생성 할 수 있게 한다.

```js
var name = "hosu", time = "today";
`Hello ${name}, how are you ${time}?`
```


## Description
- Template literals는 이중 따옴표 나 작은 따옴표 대신 백틱 (`)을 사용하여 만든다.
- Template literals는 플레이스 홀더를 이용하여 표현식을 넣을 수 있는데, 이는 `&`와 `{}`를 이용하여 `${표현식}`으로 표기할 수 있다.
- 플레이스 홀더 안에서의 표현식과 그 사이의 텍스트는 함께 함수로 전달된다.
- 태그 표현식이 처리된 Template literals과 함께 호출되면, 출력하기 전에 조작할 수 있다.
- Template literals 안의 백틱을 벗어 나려면 백틱앞에 백슬러쉬(`\`)를 넣으면 된다.

 ```js
var a = 5;
var b = 10;
console.log(`Fifteen is ${ a + b } and not ${2 * a+b}`);

```

```
Fifteen is 15 and not 20 
```

## Tagged Template
- Template literals의 발전된 형태는 tagged Templated이다.
- tagged Templated를 사용하면 template literals를 함수로 passing 할 수 있다.
- 태그 함수의 첫번째 인수는 문자열 값의 배열을 포함하고 나머지 인수는 표현식과 관련되고 결국 함수는 조작된 문자열을 반환 할 수 있다.

```js
var person = 'Mike';
var age = 28;

function myTag(strings, personExp, ageExp) {

  var str0 = strings[0]; // "that "
  var str1 = strings[1]; // " is a "

  // 사실 이 예제의 string에서 표현식이 두 개 삽입되었으므로
  // ${age} 뒤에는 ''인 string이 존재하여
  // 기술적으로 strings 배열의 크기는 3이 된다.
  // 하지만 빈 string이므로 무시한다.
  // var str2 = strings[2];

  var ageStr;
  if (ageExp > 99){
    ageStr = 'centenarian';
  } else {
    ageStr = 'youngster';
  }

  // 심지어 이 함수내에서도 template literal을 반환할 수 있다.
  return str0 + personExp + str1 + ageStr;

}

var output = myTag`that ${ person } is a ${ age }`;

console.log(output);
// that Mike is a youngster

```
