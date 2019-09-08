# JS_Object

## 객체란?
- 객체 (Object)는 값들을 그룹으로 묶은 데이터 모음입니다.
- 키(Key)와 값(Value) 한쌍으로 정의하며 이를 속성이라 합니다.
~~~
{key,value}
~~~

- 하나의 키에는 하나의 값이 매핑됩니다.
- 객체 안에 중복된 키 이름은 허용하지 않으며, 두 줄 이상의 속성을 정의할때는 콤마를 사용하여 구분합니다.

## 예시
~~~
var family = {
    'address' : 'seoul',
    members : {},
    addFamily:function(age,name,role){
        this.members[role]={
            age:age,
            name:name
        };
    },
    getHeadCount:function(){
        return Object.keys(this.members).lenght;
    }
};

family.addFamily(30,'Lee','aunt');
family.addFamily(3,'Kim','dog');
family.addFamily(10,'Park','cat');
console.log(family.getHeadCount());
~~~
- 변수 family에 중괄호를 열어 객체값을 할당하여 선언합니다.
- 키 address에 값은 문자열 'Seoul'인 속성을 객체에 추가합니다.
- 키 addFamily 이름으로 함수 리터럴을 대입합니다.
- this 키워드를 통해 family객체 내부 속성에 접근할 수 있습니다.
- 기 getHeadCount에 함수 리터럴을 할당합니다. 이 함수는 memeber의 key들을 모아 배열로 반환하고 반환된 배열의 길이를 통해 family객체의 사이즈를 알 수 있습니다.

## 예시2 ( 속성 접근/추가/수정/삭제)
~~~
var family = {
    'address' : 'seoul',
    members : {},
    addFamily:function(age,name,role){
        this.members[role]={
            age:age,
            name:name
        };
    },
    getHeadCount:function(){
        return Object.keys(this.members).lenght;
    }
};

family.addFamily(30,'Lee','aunt');
family.addFamily(3,'Kim','dog');
family.addFamily(10,'Park','cat');
console.log(family.getHeadCount());

var printMembers = function(){
    var members = family.members;
    for (role in members){
        console.log('role'=>'+role'+',name=>'+members[role].name+', age =>'+ members[role].age);
    }
};

var members = family.members;
members['nephew'] = {age:3,name:'hyun'};
members.niece = {age:5,name:'lyn'};

delete members.aunt;
delete members['cat'];
printMembers();
~~~

~~~
role => niece, name=> lyn, age=> 5
role => nephew, name=> hyun age=> 3
~~~

- 객체 속성에 접근하는 방법은 객체의 우측에 콤마. 를두고 그 다음에 객체 속성으로 정의된 키이름을 작성하면 됩니다.

## ES6의 향상된 객체 문법 - 단축 속성명
- ES6에 새롭게 추간된 기능인 단축속성명을 활용하여 좀 더 간략하게 정의 할 수 있습니다.
~~~
{변수명}
~~~
~~~

var address = 'Seoul';
var members = {};
var addFamily = function(age,name,role){
    this.members[role] = {age,name};
};
var getHeadCount = function(){
    return Object.keys(this.members).length;
};

var family = {address,memebers,addFamily,getHeadCount};

family.addFamily(30,'Lee','aunt');
family.addFamily(3,'Kim','dog');
family.addFamily(10,'Park','cat');
console.log(family.getHeadCount());
~~~
- 기존 family 객체의 속성을 변수로 저장합니다.
- 각 속성의 키 이름을 변수명으로 정의하고, 값을 해당 병수에 할당합니다.

## JSON 
- JSON(JavaScript Object Notation)은 자바 스크립트의 객체와 매우 유사한 구조를 지닌 데이터 교환 형식입니다.
- 키: 값 형태로 이루어져 있습니다.
- 반드시 key 이름은 ""로 표시된 문자열이어야 되고, 값은 오직 문자열, 숫자, 배열 , true,false, null또는 다른 JSON 객체여야합니다.
~~~
{"Key" : Value}
~~~

## 객체 속성 기술자

~~~
let user = {
    name : "hosu"
};

let descriptor = Object.getOwnPropertyDescripor(user,'name');
console.log(descriptor);
~~~
- 자바 스크립트의 모든 객체 속성은 자기 자신에 대한 정보를 담고 있는 속성기술자(PropertyDescriptor)를 가지고 있습니다.
- Object.getOwnPropertyDescriptor를 통해 속성 기술자 객체를 가지고 올 수 있습니다.

결과,
~~~
{value:"hosu", writable:true, enumerable:true, configurable:true}
~~~
~~~
let user2 = {};
Object.defineProperty(user2,"name",{
    value : "hosu", // 값을 나타낸다.
    enumerable : true, // 나열 가능 여부
    configurable : true, // 속성기술자 변경 가능 여부
    writable : false // 수정 가능 여부
});

console.log(user2.name);
user2.name = "sinjung";
console.log(user2.name);
~~~
- user2 객체를 선언하고 Object.defineProperty를 통해 해당 객체의 속성을 정의합니다.
1. value : 값을 나타냅니다.
2. enumerable : for-in 루프나 Object.key 메소드 같이 속성을 나열할때 나열 가능 여부를 정의 합니다. false인경우 나열되지 않습니다.
3. writable : 값의 수정여부를 정의합니다. false인 경우 수정되지 않습니다.
4. configurable : 속성기술자를 변경할 수 있는 여부를 정의 합니다. false인 경우 속성기술자를 다시 변경할 수 없습니다.

결과,
~~~
hosu
hosu // writable이 false로 선언되었기때문에 수정이 안된다.
~~~

~~~
let user3 = {
    name:"hosu",
    toString(){
        return this.name;
    }
}
Object.defineProperty(user3,"toString",{
    enumerable:false
});

for(let key in user3){
    console.log(key);
}
~~~
- toString 메소드로 정의하고 속성기술자를 통해 enumerable을 false로 재정의 합니다. 이렇게 되면 나열할 수 없기에 for-in 루프를 돌때에 나열되지 않습니다.
- 결과,
~~~
name
~~~

~~~
let user4 = {};
Object.defineProperty(user4,"name",{
    value : "hosu",
    configurable : false
});

delete user4.name;
console.log(user4);
Object.defineProperty(user4,"name"{
    writable : true;
})
~~~
- user4 객체에 속성기술자를 통하여 name 속성을 정의하면서 configurable 속성을 false로 하였습니다.
- configurable이 false라 delete를 통하여 name을 지우려고 하면 해당 속성이 지워지지 않고 false가 리턴됩니다.
- 새롭게 name 속성을 속성기술자로 재정의 하려면 configurable이 false이기 때문에 writable을 주어주려고 하는 문장에서 에러가 발생하게 됩니다.
결과,
~~~
{name:"hosu"}
Uncaught TypeError : Cannot readfine property: name
~~~

