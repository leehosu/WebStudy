# JS_Prototype

## 생성자 함수
- 객체를 생성하기 위해 직접적으로 객체를 반환해도 되지만, new 키워드를 사용하여 함수를 호출하게 되면 return문이 없어도 새로운 객체가 반환됩니다.
- this 키워드를 사용하여 반환되는 객체의 초기 상태와 행위를 정의 할 수 있습니다.

### 예
~~~
function Teacher(name,age,subject){
    this.name = name;
    this.age = age;
    this.subject = subject;
    this.teach = function (stuent){
        console.log(student+'에게'+this.subject+'를 알려줍니다.');
    };
}

const hosu = new Teacher('hosu',26,'JavaScrtipt');
console.log(hosu);
hosu.teach('lake');
~~~
### 결과
~~~
Teacher {name: "hosu", age: 26, subject: "JavaScrtipt", teach: ƒ}lake에게JavaScrtipt를 알려줍니다.
~~~

### 생성자 함수의 new 호출을 통한 객체 생성 과정
1. 빈객체를 만든다.
2. 만든 빈 객체를 this에 할당한다.
3. 생성자 함수 바디의 코드를 실행한다.
4. 만든 빈 객체의 __proto__에 생성자 함수의 prototype 속성을 대입한다.
5. this를 생성자의 반환값으로 변환한다.

## 프로토타입 기반 상속
- 자바 스크립트에서 생성자 함수로부터 만들어진 객체는 그 생성자 함수의 프로토타입 객체를 상속합니다.
-> 모든 인스턴스는 해당 생성자 함수의 프로토타입 객체의 속성과 메소드들을 사용할 수 있습니다.
- 모든 객체는 '_ _proto_ _' 속성을 가지는데 이 속성은 해당 객체를 생성한 생성자 함수의 prototype 객체를 가리킵니다.

### 예
~~~
function Storage(){
    this.dataStore = {};
}

Storage.prototype.put = function(key,data){
    this.dataStore[key] = data;
}
Storage.prototype.getData = function(key){
    return this.dataStore[key];
}

const peopleStorage = new Storage();
peopleStorage.put('hosu',{name:'호수',age:26});
console.log(peopleStorage.getData('hosu'));

function removeStorage(){
    Storage.call(this);
}
removeStorage.prototype = Object.create(Storage.prototype);

removeStorage.prototype.removeAll = function{
    this.dataStore = {}
}

const peopleStorage = new removeStorage();
peopleStorage.put('hosu',{name:'호수',age:26});
peopleStorage.removeAll();
~~~
