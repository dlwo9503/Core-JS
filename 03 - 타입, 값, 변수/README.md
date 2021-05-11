## [2021-05-11] 3장 타입, 값, 변수 
### 3. 도입부
- 자바스크립트의 타입은 크게 원시 타입과 객체 타입으로 나뉘고, 원시 타입으로는 숫자, 텍스트의 나열(문자열), 불리언이 있다. 
- 자바스크립트에서 null과 undefined는 원시값이긴 하지만, 숫자도 아니고, 문자열이나 불리언도 아니다. 자바스크립트에서 null과 undefined는 자기 자신만을 값으로 갖는 독립적인 타입에 속한다.
<br/>

### 3.1 숫자
- JS는 다른 프로그래밍 언어들과는 다르게 JS는 정수 값과 실수 값을 구분하지 않는다. JS는 모든 숫자를 실수로 표현한다. IEEE 754 표준에서 정의한 64비트 실수 형태로 표현한다.
<br/>

### 3.1.1 정수 리터럴
JS에서 10진수 정수는 숫자를 일렬로 나열한 것이다. 예를 들면, 다음과 같다.
- 0
- 3
- 10000000
JS는 10진수 리터럴 이외에도 16진수 값을 인식한다.
<br/>

### 3.1.2 부동소수점 리터럴
부동소수점 리터럴은 소수점을 가질 수 있다. 부동소수점 리터럴은 실수를 표현하는 전통적인 문법을 따른다. 
실수는 정수 부분과 소수점, 소수점 이하 부분으로 표현한다.
부동소수점 리터럴은 지수 표기법으로도 표현할 수 있다.
- 3.14
- 2345.789
- .333333333
<br/>

### 3.1.3 산술 연산
JS에서는 언어에서 제공하는 산술 연산자를 사용하여 숫자를 다룬다. 산술 연산자로는 덧셈을 위한 +와 뺄셈을 위한 -, 곱셈을 위한 *, 나눗셈을 위한 /와 나눗셈 연산을 한 후 나머지를 구하는 % 연산자가 있다.
더 복잡한 수치 연산을 Math 객체를 통해 지원한다.

![image](https://user-images.githubusercontent.com/74044292/117760063-eba49080-b25f-11eb-97d1-6c8eb84dc543.png)

<br/>

### 3.1.5 날짜와 시간
코어 자바스크립트는 날짜와 시간을 표현하는 객체를 생성하는 Date() 생성자를 제공한다. Date 객체는 간단한 날짜 계산을 하는 메서드를 가지고 있다.
Date 객체는 숫자 같은 원시 타입이 아니다.

![image](https://user-images.githubusercontent.com/74044292/117760557-d11ee700-b260-11eb-9694-6642e4bc2e61.png)
<br/>

### 3.2.2 문자열 리터널 내의 이스케이프 문자열
역슬래쉬 문자는 자바스크립트 문자열에서 특별한 목적을 위해 사용한다. 예를 들어 \n은 줄바꿈 문자를 나타내는 이스케이프 시퀀스다.
<br/>

### 3.2.3 문자열 다루기
자바스크립트가 지원하는 기본 기능 중 하나는 여러 문자열을 이어붙이는 것이다. 숫자에 + 연산자를 적용하면 숫자들이 더해진다.
하지만 문자열에 적용하면 두 번째 문자열을 첫 번째 문자열에 이어 붙인다.
```txt
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
<br/>
