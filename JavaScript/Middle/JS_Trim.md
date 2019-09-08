# Trim()

- String 내장 객체의 `trim()` 메소드는 문자열 양 끝의 공백, 탭, 줄바꿈을 제거한다. 단, 함수가 적용된 문자열 원본 값에는 영향을 끼치지 않기 때문에 활용하려면 별도로 값을 저장해야한다.

### Example
```js
const sentences = ['    ABC abc', 'ABC abc  ',`first
second third
        forth
sentence
`];

const filterSentence = (sentences) => {
    const filtered = [];
    sentences.forEach(s => {
        filtered.push(s.trim());
    });

    return filtered;
}

console.log(filterSentence(sentences));
```

##### code run
```
[ 'ABC abc',
  'ABC abc',
  'first \nsecond third\n   forth\nsentence'
]
```
- filterSentence함수는 매개변수로 전달된 배열을 `forEach`로 순환하면서 각 요소에 접근한다. 그 때 배열 요소에 `trim()`을 적용하여 공백, 탭, 줄바꿈을 삭제하고 필터링된 값을 다시 배열로 반환한다.

