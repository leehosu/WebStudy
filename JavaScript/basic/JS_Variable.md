# JS_Variable

## 👁 변수 범위 (Variable Scope)
- 변수가 존재하는 context.

## 👌 지역 변수(함수 수준 범위)
- 자바 스크립트는 다른 언어와 달리 블럭 수준(block-level)의 범위를 갖고 있지 않다.
- 대신 javascript는 함수 수준(function-level)을 갖는다.
- 함수내에서 정의된 변수는 지역 범위를 가지며, 해당 함수와 내부 함수에서만 접근가능하다.

## 👌 전역 변수
- 함수의 외부에서 선언된 모든 변수는 전역 범위(global scope)를 가진다.
- 전체 어플리케이션에서 사용 가능.
~~~
var name = "Rechard";   //전역 변수

function showName(){
    var name = "Jack";  //지역변수
    console.log(name);  //Jack
}

console.log(name);  // Rechard
~~~

~~~
var name = "Lee Hosu";

function showFirstName(){
    console.log(name);
}

function showSecondName(){
    name = "Lim Hosung";
    console.log(name);
}

showFirstName();    //Lee Hosu

showSecondName();   //Lim Hosung

function literalName(){
    var name = "Joe Dea hee";   //전역 변수를 덮어쓰지 않고 지역변수로 지정.
    console.log(name);
}

~~~
! 지역변수는 함수내에서 전역 변수보다 높은 우선 순위를 가진다.

## 🛠 변수 호이스팅 (Variable Hoisting)
- 호이스트란, 변수의 정의가 그 범위에 따라 선언과 할당으로 분리되는 것을 의미한다.
- 변수가 함수 내에서 정의 되었을 경우 선언이 함수의 최상위로, 함수 밖에서 정의 되었을 경우에는 전역 컨텍스트의 최상위로 변경된다.
- 변수의 선언이 초기화나 할당시에 발생하는 것이 아니라, 최상위로 호이스트된다.
- ##### 선언과 할당을 이해해야 한다.

~~~
function getString(){
    console.log(tmp);     //undefind
    var tmp = 100;
    console.log(tmp);     //100
}
getString();
~~~

- 다른 언어의 경우에는 이 코드는 오류를 나타낸다. 하지만 JS는 undefind이라 출력하고 넘어간다.
- ##### var x = 100 이 부분에서 var x를 호이스트했기 때문이다.
~~~
function getX(){
    var x;
    console.log(x);     //undefind
    x = 100;
    console.log(x);     //100
}
getX();
~~~
######즉, JS에서는 이렇게 구동된다.
- 함수 호이스팅은 함수를 끌어올리지만 변수 값은 끌어올리지 않는다.
-> 함수 표현식에서는 함수 리터럴을 할당하는 구조이기 때문에 호이스팅 되지않는다!!!

## 🤞식별자(Identifier) VS 리터럴(literal)
- 리터럴 : 값을 프로그램안에서 직접 지정.
- 식별자 : 변수, 함수 혹은 프로퍼티를 식별하는 문자열.

## 🤷‍ var,let,const란?
- var,let은 변수를 선언하는 키워드이고, const는 상수를 선언하는 키워드이다.
- var,let은 리터럴 값의 재할당이 가능하지만, const는 리터럴값의 재할당이 불가능하다.
- 중괄호 내부에 let,const 키워드로 선언된 변수는 외부 스코프에 영향을 주지 않는다.

## 🌹 var VS let VS const
- var 키워드는 변수명을 재선언해도 아무런 문제가 발생하지 않는다.
- let 키워드는 변수명 재선언시 에러를 발생시킨다.
- let 키워드와 전반적으로 유사하며, 단지 상수 선언 용이므로 리터럴값을 재 할당하는 것이 불가능하며 선언과 동시에 값 할당해야한다.
###### - var 키워드는 javascript 해석기가 호이스팅을 통해 재 해석한다. -> 막기 위해서 js scope(전역/함수)에 use strict를 사용해야 한다.

즉, let키워드는 변수의 재 선언을 막아주고 호이스팅이 되지않으므로 사용전 먼저 선언해야한다.
