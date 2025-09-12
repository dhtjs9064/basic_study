JS에서 출력할때는 "console.log();"를 사용한다.

## 1. 변수

```js
name = "sun";
age = 99
name = "sea";
```

이런 형식으로 선언하고 세미콜론은 안붙여도 정상 동작한다.  
(일반적으로는 붙인다고 한다.)  

### let
```js
let name = "sun";
let name = "sea";
```

let은 이 변수로 선언한다는 뜻으로 다른 변수가 덮어 씌울 수 없다.
```js
let name = "sun";
name = "sea";
```
하지만 이렇게 의도적으로 변경하려한다면 바꾸기가 가능하다.  

### const
```js
const PI = 3.14;
```

const는 상수로 선언하려할 때 사용한다.  
즉, 변하지 않는 값이다.  
Java의 final과 비슷한 느낌이다.  

- 정리  
결국 변하지 않는값은 const,
변할 수 있는 값은 let으로 적어두면된다.

## 2. 자료형

### 문자형
```js
const name = "Mike";
const name = 'Mike';
const message = ", Hi";

const meesage2 = `My name is ${name}${message}`; // My name is Mike, hi

console.log(meesage2);
```
문자형은 이런식으로 "", '', ``으로 표현할 수 있으며,  
문자열에 변수를 넣고 싶을때 "${변수}"와 같은 형식으로 넣을 수 있다.

### typeof 연산자
```js
console.log(typeof 5); // number
console.log(typeof "name"); // string
console.log(typeof true); // boolean
```
이럴 경우 각각 자료형의 타입을 알 수 있다.  
같이 개발하는 개발자가 만든 자료형의 타입이 무엇인지 유추하는 식으로 사용할 수 있다.

## 3. 대화상자

### alert, prompt, confirm
<img width="578" height="346" alt="image" src="https://github.com/user-attachments/assets/5b665daf-ec87-4ac9-a583-8738138e3f1e" />  

prompt()는 대화상자를 생성하여 입력값을 넣을 수 있도록하고,

<img width="578" height="346" alt="image" src="https://github.com/user-attachments/assets/d3f6b3f6-f2cc-4eb5-b4eb-22908ee9e192" />

alert()는 대화상자를 생성하는데 그저 알림창 역할만 한다.  

추가로 prompt()는 prompt("문자열", "여기서 입력"); 이런식으로 뒤에 인수를 넣었을때 입력창에 그대로 뒷 인수내용이 뜨게할 수 있다.

<img width="578" height="385" alt="image" src="https://github.com/user-attachments/assets/da3fc0c3-b74b-45d3-b9ae-9ba78a3b2c79" />

confirm()은 alert()와 달리 취소, 확인버튼이 있어 사용자에게 선택권을 준다.  
확인 = true, 취소 = false의 결과값을 얻는다.

## 4. 형변환

### Number() 
```js
console.log(
Number("1234")
);
```
이런식으로 문자형 숫자를 쓰면 자동으로 형변환되지만,  
문자열이 들어가면 **NaN** 즉, Not a Number가 뜨게된다.  
추가로, Number(null) = 0이지만, Number(undefined) = NaN 이다.

### Boolean()
```js
console.log(
Boolean(0),
Boolean(""),
Boolean(null),
Boolean(undefined),
Boolean(NaN)
);
```
Boolean()은 0, "", null, undefined, NaN일 경우 전부 **false**이다.

## 5. 함수

### 함수 선언문 vs 함수 표현식

- 함수 선언문
```js
function hello(name) {
console.log(`Hello, ${name}`);
}
```

- 함수 표현식
```js
let hello = function (name) {
console.log(`Hello, ${name}`);
}
```
차이 : 
함수 선언문은 자바의 함수와 같이 먼저 호출해도 순서에 상관없이 호출(hoisting)이되지만,  
함수 표현식은 먼저 호출하면 함수를 찾지 못해 오류가 난다.

### 화살표 함수
```js
let add = (num1, num2) => {
num1 + num2;
}
```
즉, function을 "=>"로 바꾸고 매개변수 뒤에 쓰기만 하면된다.

## 6. 객체
```js
const animal = {
name : "popo",
age : 5,
}
```
이런식으로 구성되며, 내부에는 "키 : 값" 형식으로 이루어져있다.  

그런데 만약,
```js
const name = "name";
const age = 3;

const animal = {
name : name,
age : age,
}
```
이렇게 키와 값의 이름이 동일하다면  

더 간편하게
```js
name,
age,
```
이와같은 형식으로 쓸 수 있다.  
이것은 함수에서도 동일하게 이용 가능하다.  

- 참조할때
객체를 참조할때는
animal.name 혹은,
animal[name]과 같이 2가지 방식으로 참조할 수 있다.  

.name을 사용하면 name이라는 문자열을 가진 키를 animal에서 찾는것이고,  
[name]을 사용하면 name이라는 변수에 키 값을 넣어 찾는다는 뜻이다.


- 객체 in
in을 사용해서 해당 프로퍼티가 객체안에 있는지 확인할 수 있다.
예를들어,
```js
const animal = {
name : "popo",
age : 5,
}

console.log("name" in animal); // true
```

이런식으로 특정 키가 있는지 없는지 확인할 수 있다.  
이를 활용해 for...in을 활용할 수 있는데,  
```js
const animal = {
name : "popo",
age : 5,
}

for(a in animal) {
console.log(animal[a]); // animal['name'] = "popo", animal['age'] = 5
}
```
이렇게 animal안의 모든 값을 알아낼 수 있다.  
for ... in은 이렇게 객체를 순회할 수 있다.
