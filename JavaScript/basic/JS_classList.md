# JS_classList

## Element.JS_classList
- 요소의 클래스 속성의 컬렉션인 활성 DOMTokenList를 반환하는 읽기전용 프로퍼터입니다.
- classList 사용은 공백으로 구분된 문자열인 element.clssNmae을 사용하여 클래스들의 목록에 접근하는 방식을 대체하는 간편한 방법입니다.

## 구문
~~~
const elementClasses = elementNodeReference.classList;
~~~
-> elementClasses는 elementNodeReference의 클래스 속성을 나타내는 DOMTokenList입니다. 만약 클래스 속성이 설정되어있지 않거나 비어있다면 elementClasses.length는 0을 반환합니다.


## method
1. add (String [,String])
- 특정 클래스 값을 추가합니다.
만약 존재한다면 무시됩니다.
2. remove(String[,String])
- 특정 클래스 값을 제거합니다.
3. item(Number)
- 클래스 값을 콜렉션의 인덱스를 이용하여 반환합니다.
4. toggle (String [,force])
- 한개의 인숨나 있을때 : 클래스 값을 변환합니다.
( 클래스가 존재한다면 지우고 false를 반환, 존재하지 않다면 추가하고 true를 반환)
- 두번째 인수가 있을때 : 두번째 인수가 true로 평가되면 특정 클래스 값을 추가하고 false로 평가되면 지웁니다.
5. contains (String)
- 특정 클래스 값이 요소의 클래스 속성에 존재하는지 확인합니다.
6. replace (oldClass, newClass)
- 기존의 클래스를 새로운 클래스로 교체합니다.

## 예제
~~~
var element = document.getElementById( 'element' );

element.classList.add( 'someclass' );
element.classList.add( 'someclass1', 'someclass2' );
element.classList.remove( 'someclass' );
element.classList.remove( 'someclass1', 'someclass2' );
element.classList.contains( 'someclass' );
element.classList.contains( 'someclass1', 'someclass2' );
element.classList.toggle( 'someclass' );
~~~   
