# 6장. 객체

#### 객체(object)
객체 : 프로퍼티(property)의 집합
  * 프로퍼티 : {이름 , 값}
    * 이름 : 문자열
    * getter,setter 포함
    * 동적으로 생성 및 제거 가능
  * 프로토타입 상속 : 다른 객체 프로퍼티 상속받음
    * 프로토타입(prototype) : 참조 대상

```js
var y = x; // y는 x 객체 참조
```

객체 3가지 종류
1. native object
  * Array, Function, Date, RegExp, ...
2. host object
  * 브라우저처럼 호스트 환경에 정의된 객체
3. user-defined object
  * JS 코드 실행으로 생성된 객체


#### 프로퍼티(property)

프로퍼티 속성(property attribute)
* writable : 수정 여부
* enumerable : 프로퍼티 이름을 for/in에서 읽을 수 있는 지 여부
* configurable : 삭제 가능 여부, 속성 변경 여부

#### 프로토타입(prototype)
프로토타입 체인
```js

```

## 1. 객체 생성하기

### 1-1. 객체 리터럴 사용

객체 리터럴

* 변수 = { 이름 : 값 }

```javascript
var empty = {}; //빈 객체
var point = { x: 0, y: 0 }; //두 개 property x,y
var book = {
  "main title": "JavaScript",
  "sub-title": "The Definite Guide",
  author: {
    firstname: "David",
    surname: "Flangan"
  }
};

console.log(empty); //{}
console.log(point); //{x: 0, y: 0}
console.log(book); //{main title: "JavaScript", sub-title: "The Definite Guide", author: Object}
console.log(book.author); //{firstname: "David", surname: "Flangan"}
```

### 1-2. new 사용
new 연산자 : 객체 만듦과 동시에 생성자 호출
```js
var o = new Object();
var a = new Array();
var d = new Date();
var r = new RegExp("js");

console.log(o); //{}
console.log(a); //[]
console.log(d); //Tue May 11 2021 13:33:43 GMT+0900 (대한민국 표준시)
console.log(r); // /js/
```
### 1-3. Object.create() 사용
Object.create() : 객체 생성 메서드
```js
var o1 = Object.create({x:1,y:2}); //o1는 x,y프로퍼티 상속받음
var o2 = Object.create(null); //o2는 프롵토타입 갖지 않은 객체
var o3 = Object.create(Object.prototype); //o3는 빈객체 ({}나 new Object()로 만든 것과 동일)
```

## 2. 프로퍼티 접근 및 설정
### 접근
```js
var author = book.author;
var title = book.["main title"];
```
### 설정
```js
book.edition = 6;
book["main title"] = "ECMAScript";
```
