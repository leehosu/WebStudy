# JS_Clouser

##🛠클로저란?(clouse)
- 클로저는 외부함수(포함하고 있는)의 변수에 접근할 수 있는 내부 함수를 뜻한다.
- 클로저는 3가지 스코프 체인을 가진다.
    1. 클로저 자신에 대한 접근(자신의 블럭 내에 정의된 변수)
    2. 외부 함수에 대한 접근
    3. 전역 변수에 대한 접근

~~~
function showName(firstName, lastName){     //외부 함수
    var nameIntro =" My Name Is ";  //외부함수에 선언된 지역 변수

    function MakeName(){    //내부 함수
        return nameIntro + firstName + lastName;
    }
    return MakeName();
}
showName("Lee","Host");
~~~
- 내부함수에서 외부함수의 지역변수에 접근 할 수 있다.
- 외부함수가 종료된 이후에도 내부함수가 외부함수에 접근할 수 있다.

~~~
function outerFunc(){
    var x = 10;
    var innerFunc = function(){
        console.log(x); //10
    };

    innerFunc();
}

outerFunc(); //10
~~~
- 함수 outerFunc 내에서 내부 함수 innerFunc가 선언되고 호출되었습니다. 이때 내부함수 innerFunc는 자신을 포함하고 있는 외부함수 outerFunc의 변수 x에 접근 할 수 있습니다.

~~~
function outerFunc(){
    var x = 10;
    var innerFunc = function(){
        console.log(x);
    };
    return innerFunc;
}
outerFunc();
// outerFunc를 호출하면 내부 함수 innerFunc가 반환된다.
// 그 후 함수 outerFunc의 실행 컨텍스트는 소멸합니다.

var inner = outerFunc();
inner(); //10
~~~

- 함수 outerFunc는 내부 함수 innerFunc를 호출하고 소멸했습니다.
- 즉, 함수 outerFunc는 실행된 이후 콜스택에서 제거 되었으므로 변수 x또한 더 이상 유효하지 않게 되어 접근할 방법이 없어져보입니다.
- 하지만 자신을 포함하고 있는 외부함수 보다 내부함수가 더 오래 유지되는 경우, 외부 함수 밖에서 내부함수가 호출되더라도 외부함수의 지역 변수에 접근 할 수 있는데 이러한 함수를 클로저 라고 부릅니다.

##### 클로저는 반환된 내부함수가 자신이 선언되었을때의 환경인 스코프를 기억하여 자신이 선언되었을때의 환경 밖에서 호출되어도 그 환경에 접근 할 수 있는 함수.
