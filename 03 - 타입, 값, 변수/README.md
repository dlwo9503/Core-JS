# [2021-05-11] 3장 타입, 값, 변수
## 3. 도입부
- 자바스크립트의 타입은 크게 원시 타입과 객체 타입으로 나뉘고, 원시 타입으로는 숫자, 텍스트의 나열(문자열), 불리언이 있다.
- 자바스크립트에서 null과 undefined는 원시값이긴 하지만, 숫자도 아니고, 문자열이나 불리언도 아니다. 자바스크립트에서 null과 undefined는 자기 자신만을 값으로 갖는 독립적인 타입에 속한다.
<br/>

### 3.1 숫자
- JS는 다른 프로그래밍 언어들과는 다르게 JS는 정수 값과 실수 값을 구분하지 않는다. JS는 모든 숫자를 실수로 표현한다. IEEE 754 표준에서 정의한 64비트 실수 형태로 표현한다.
<br/>

#### 3.1.1 정수 리터럴
JS에서 10진수 정수는 숫자를 일렬로 나열한 것이다. 예를 들면, 다음과 같다.
- 0
- 3
- 10000000
JS는 10진수 리터럴 이외에도 16진수 값을 인식한다.
<br/>

#### 3.1.2 부동소수점 리터럴
부동소수점 리터럴은 소수점을 가질 수 있다. 부동소수점 리터럴은 실수를 표현하는 전통적인 문법을 따른다.
실수는 정수 부분과 소수점, 소수점 이하 부분으로 표현한다.
부동소수점 리터럴은 지수 표기법으로도 표현할 수 있다.
- 3.14
- 2345.789
- .333333333
<br/>

#### 3.1.3 산술 연산
JS에서는 언어에서 제공하는 산술 연산자를 사용하여 숫자를 다룬다. 산술 연산자로는 덧셈을 위한 +와 뺄셈을 위한 -, 곱셈을 위한 *, 나눗셈을 위한 /와 나눗셈 연산을 한 후 나머지를 구하는 % 연산자가 있다.
더 복잡한 수치 연산을 Math 객체를 통해 지원한다.

![image](https://user-images.githubusercontent.com/74044292/117760063-eba49080-b25f-11eb-97d1-6c8eb84dc543.png)

*  overflow 대신 Infinity, underflow 대신 -Infinity
* 0으로 나누었을 때, error X : Infinity 반환
  * cf ) 0/0 : NaN

<br/>

#### 3.1.5 날짜와 시간
코어 자바스크립트는 날짜와 시간을 표현하는 객체를 생성하는 Date() 생성자를 제공한다. Date 객체는 간단한 날짜 계산을 하는 메서드를 가지고 있다.
Date 객체는 숫자 같은 원시 타입이 아니다.

![image](https://user-images.githubusercontent.com/74044292/117760557-d11ee700-b260-11eb-9694-6642e4bc2e61.png)
<br/>

#### 3.2.2 문자열 리터널 내의 이스케이프 문자열
역슬래쉬 문자는 자바스크립트 문자열에서 특별한 목적을 위해 사용한다. 예를 들어 \n은 줄바꿈 문자를 나타내는 이스케이프 시퀀스다.
<br/>

#### 3.2.3 문자열 다루기
자바스크립트가 지원하는 기본 기능 중 하나는 여러 문자열을 이어붙이는 것이다. 숫자에 + 연산자를 적용하면 숫자들이 더해진다.
하지만 문자열에 적용하면 두 번째 문자열을 첫 번째 문자열에 이어 붙인다.
```js
msg = "hello," + "world"; // 문자열을 합친다. "Hello, world"
var s = "hello, world" // Start with some text.
s.charAt(0) // => "h": the first character.
s.charAt(s.length-1) // => "d": the last character.
s.substring(1,4) // => "ell": the 2nd, 3rd and 4th characters.
s.slice(1,4) // => "ell": same thing
s.slice(-3) // => "rld": last 3 characters
s.indexOf("l") // => 2: position of first letter l.
s.lastIndexOf("l") // => 10: position of last letter l.
s.indexOf("l", 3) // => 3: position of first "l" at or after 3
s.split(", ") // => ["hello", "world"] split into substrings
s.replace("h", "H") // => "Hello, world": replaces all instances
s.toUpperCase() // => "HELLO, WORLD"
```
* replace(), toUpperCase() : 새 문자열 반환

#### 3.2.4 패턴 매칭

문자열, RegExp는 패턴 매칭 메서드 제공

RegExp 객체 ([10장 참고](https://github.com/Definitive-JS/Core-JS/tree/master/10%20-%20%EC%A0%95%EA%B7%9C%20%ED%91%9C%ED%98%84%EC%8B%9D%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%9C%20%ED%8C%A8%ED%84%B4%20%EB%A7%A4%EC%B9%AD))
* 원시 타입 X (기본 데이터 타입 X)
* 형태 : /\\내용/
* 패턴 매칭 메서드 : 정규 표현식(문자 패턴) 매칭
* 검색 후 바꾸기 메서드

```js
var text = "testing: 1,2,3"; //문자열
var pattern = /\d+/g //정규표현식 리터럴;하나 이상의 모든 숫자와 일치
pattern.test(text); //true
text.search(pattern); //9 - 첫 번째로 매치하는 문자열 위치
text.match(pattern); //["1","2","3"] - 일치된 항목
text.replace(pattern,"#"); //"testing: #, #, #"
text.split(/\D+/); //["","1","2","3"] : 숫자 아닌 문자 기준으로 분할
```

### 3.3 불리언 값

true, false

```js
//false인 값들
undefined
null
0
-0
NaN
""
```

### 3.4 null and undefined

null : 아무 값도 갖지 않음을 가리킬 때 사용
* 예상가능한 값의 부재
  * 보통 객체에 대해 "객체가 없음"을 뜻하게 할 떄 사용
  * 현업에서는 숫자,문자열에도 사용되어 "값이 없음"을 나타내는 데에 쓰임

undifined : null보다 심한 부재 상태
* 오류성 값 부재
  * 초기화 되지 않은 변수 접근
  * 존재하지 않는 객체 프로퍼티 접근
  * 존재하지 않는 배열의 원소값에 접근

### 3.5 전역 객체 (:star:)

인터프리터 시작시, 새로운 전역 객체를 만들어 초기화한 뒤 스크립트 프로그램 전역에서 사용할 수 있다.

```js
//전역 프로퍼티 - 예약어가 아니지만 예약어처럼 사용
undefined
Infinity
NaN
//전역 함수
isNaN()
parseInt()
eval()
//생성자 함수
Date()
RegExp()
String()
Object()
Array()
//전역 객체
Math
JSON
```

```js
var global = this; //전역 객체 참조 변수 this
```

클라이언트 측 JS의 Window 객체 : 전역 객체
* 브라우저 창의 모든 JS코드내에서 사용
* window 프로퍼티 : Window 자기자신 참조 (this대신 사용)

### 3.6 Wrapper 객체

wrapper객체
* 문자열, 숫자, 불리언의 프로퍼티 접근시, 생성되는 임의의 객체
  * 문자열, 숫자, 불리언 값이 프로퍼티는 읽기 전용이고, 새로운 프로퍼티를 정의할 수 없다.

```js
var s = "test";
s.len = 4;  //wrapper(임시객체)에 값 할당 후 바로 삭제
var t = s.len; //t : undifined ; "test"와 같은 문자열 값 가지는 새 String 객체 생성 - 해당 객체는 len property가 없음
```

### 3.7 변경 불가능한 원시 타입 값과 변경 가능 객체 참조

|    |원시 타입|객체|
|----|----|----|
|종류|undifined,null,불리언,숫자,문자열|배열,함수|
|차이점|수정 불가(immutable)|수정 가능(mutable)|
|값과 참조|<pre class="javascript"><code>var a = 1;//값<p>var b = 1;//값<p>console.log(a===b); //true</code></pre>|<pre><code>var a = {x:1};//참조<p>var b = {x:1};//참조<p>console.log(a===b);//false</code></pre>|

### 3.8. 타입변환

* JS는 타입변환이 유연한 편
* null,undifined는 변환 불가능

```js
10 + " 11" //문자열; 10 11 (10이 문자열로 변환)
"7" * "4" //숫자; 28 (두 문자열은 숫자로 변환되어 계산)
var n = 1 - "x" //NaN; 문자열x는 숫자로 변환 불가능
n + " objects" //문자열; "NaN objects" (NaN인 n은 문자열"NaN"으로 변환됨)
```
#### 3.8.1. 변환과 동치

* == : 비교하려는 값이 서로 변환가능하다면 변환해서 비교
  ```js
  //모두 true
  null == undefined
  "0" == 0
  ```
* === : 타입변환을 하지 않고 엄격하게 비교

#### 3.8.2. 명시적 변환

코드를 깔끔하게 하기 위해 명시적 변환 선호

```js
Number("3") //숫자 3
ParseInt("3 blind") //숫자 3
ParseInt("bli li") //NaN
```

#### 3.8.3. 객체 -> 원시타입
```js
//toString()
[1,2,3].toString() //"1,2,3"
({x:1,y:2}).toString() //"[object Object]"

//valueOf()
var d = new Date(2010,0,1);
d.valueOf() //126233280000 (1970.1.1부터2010.1.1까지 밀리초)
```

### 3.9 변수 선언

var 키워드 사용 : 타입 명시하지 않음

```js
var i;
var message = "hello";
```

### 3.10. 변수의 유효범위

Scope
* 변수가 정의되어 있는 영역
  * global variable
    * var 키워드 없어도 됨
  * local variable
    * var 키워드 있어야 함
    * global과 같은 이름이라면 local이 우선시됨
