# Global Object

- 자바 스크립트에는 ECMAScript 구현 명세에 의해 정의된 표준 내장 객체가 있다. 
- 표준 내장 객체는 전역 스코프 안에 있는 객체들을 참조하고 있어, 자바스크립트를 실행 할 때 어떤 환경(브라우저, 서버)이라도 전역에서 사용 가능하다.

- 몇몇 표준 내장 객체는 객체임에도 불구하고 함수처럼 호출할 수 있다. 이러한 형태를 **내장 함수 객체**라고 한다.
- new 지시자를 사용하여 함수 형태로 호출하며, 생성자를 생성한다.

### Example
```js
const str = new String('자바스크립트');
const num = new Number(200);
const boll = new Boolean(true);
const date = new Date();
const map = new Map();
const set = new Set();

console.log(Math.PI);
console.log(Date.parse('2019-09-08'));
console.log(JSON.parse('{}'));
```

##### code run
```
3.14159265
1546300
{}
```

- 자바스크립트 표준 내장 객체의 종류에 대해 살펴보면,
    - **Object** : 다른 표준 내장 객체의 기본이 되는 일반 객체
    - **Number** : 숫자형을 감싼 객체. 숫자형과 관련된 함수와 속성을 갖고 있다.
    - **String** : 문자형을 감싼 객체. 문자형을 조작하거나 특정 문자열을 찾고 추출하는 등의 메소드와 속성을 활용할 수 있다.
    - **Array** : 모든 배열 Array.prototype을 상속 받는다. Array 객체는 리스트처럼 배열 역할을 지니며, 배열 요소를 추가/삭제 하거나, 배열 자체를 순회/ 변형하는 다양한 메소드 속성을 지니고 있다.
    - **Math** : 수리 연산을 하기 위한 속성과 메소드를 지닌 내장 객체이다. 다른 내장 객체와 달리 Math객체는 new를 통해 인스턴스를 생성하지 않는다. static으로 정의된 속성과 메소드를 직접 호출해야한다.
    - **JSON** : JavaScript Object Notation을 의미하며 다른 자료형을 변환하거나 다시 JSON으로 변환하는 등의 메소드를 제공한다.
    - **RegEXP** : 정규표현식은 특정 문자열 처리를 위해 사용하는 문자열 패턴 정의를 의미한다. 정규표현식을 적용 가능한 문자열 탐색, 비교, 대체 등의 문자열 처리 메소드들을 지원한다.
    - **Map** : ES6부터 표준으로 추가된 Map 객체는 `key:value` 데이터 구조를 지닌 데이터 집합체이다. 키의 중복성을 허용하지 않으며 관련된 속성, 메소드들을 갖고 있다. 또한 Iterator를 통해 Map의 데이터를 순회한다는 특징이 있다.
    - **Set** : ES6부터 표준으로 추가된 객체형으로 오직 값으로 이루어진 데이터 집합체이다. 그래서 언뜻 배열과 비슷하게 느껴질 수 있으나 내부 속성, 메소드의 구성이 다르고, 또한 Iterator로 순회한다는 점, 값의 중복성을 허용하지 않는 차이가 있다.

### Example
```js
const str1 = '이호수만세';
const str2 = new String('이호수만세');

console.log(typeof str1);
console.log(typeof str2);

console.log(str1 === '이호수만세');
console.log(str2 === new String('이호수만세'));

console.log(str1.valueOf());
console.log(str2.valueOf());
```

##### code run
```
string
object
ture
false
이호수만세
이호수만세
```
- `valueOf` 메소드는 String 내장 객체에 정의된 메소드로, 객체의 원시형 값, 즉 문자열을 반환하는 메소드이다.