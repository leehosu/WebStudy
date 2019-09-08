# JS_Exception

## 예외 처리하기
- 자바 스크립트 코드를 실행하다 에러가 발생하면 그 즉시 중단됩니다.
- 예외 방법 처리에는 throw문 , try-catch-finally 문이 있습니다.
- 예외의 처리에는 2가지로 나누는데 1. 예상치 못한 에러 2. 개발자가 의도한 에러가 있습니다.

1. 개발자가 의도한 에러 - throw
~~~
function checkNumver(val){
    if(typeof val !== 'number') throw '유효하지 않습니다.';
    // typeof val을 통해 숫자형 값이 아닌경우 throw문을 통해 빠져나갑니다.
    console.log('숫자형으로 확인되었습니다.');
}

checkNumber(100);
checkNumber('wrong type');
console.log('완료');
~~~

결과는,
~~~
숫자형으로 확인되었습니다.
/test/test1/ex07.js:2   
    if(typeof val !== 'number') throw '유효하지 않습니다.';
                                  ^
유효하지 않는 값입니다.
~~~
즉, throw문은 예외 상황을 미리 파악하고 에러를 발생시켜 이후 코드가 실행되지 않도록 합니다.

2. 예상치 못한 에러 - try - catch - finally
- try 블록 안에서 발생된 에러를 잡아내고 , catch 블록으로 제어권을 넘깁니다. finally 블록은 에러 발생여부와 상관없이 실행되는 블록입니다.

~~~
function checkNumver(val){
    if(typeof val !== 'number') throw '유효하지 않습니다.';
    // typeof val을 통해 숫자형 값이 아닌경우 throw문을 통해 빠져나갑니다.
    console.log('숫자형으로 확인되었습니다.');
}

try{
    checkNumber(100);
    checkNumber('wrong type');
}catch(e){
    console.log(`에러가 발생했습니다 >>> ${e}`);
}finally{
    console.log('완료');
}
~~~