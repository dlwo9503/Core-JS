1 표현문
 - 표현식을 인터프리터가 실행할 수 있도록 문장 형태로 만들어줘야 하는데, 이 결과로 만들어진 문장이 '표현문'이다.
 - 문장의 끝은 마침표(.) 로 끝나듯이, 자바스크립트 표현문의 끝은 세미콜론(;) 으로 나타낸다.
 - 할당문   
ex) greeting = "Hello " + name;
 - 함수호출   
ex) alert('Hello');

2 복합문과 빈 문장
 - 하나의 표현식 안에 여러 표현식을 합칠 때는 쉼표(,) 연산자나 문장 블록을 사용한다.
 - 문장 블록은 세미콜론(;)으로 끝나지 않고, 중괄호({})로 감싸준다.   
ex) int a = 1, b = 2;   
ex) {
    x = Math.PI;
    cx = Math.cos(x);
    console.log("cos(x) = " + cx);
}

3 선언문
 - var : var문은 하나 또느 그 이상의 변수를 선언한다.   
ex) var 변수이름 = 값   
 - function : function 키워드는 함수를 정의하는데 사용한다.   
ex) function 함수이름([전달인자1 [, 전달인자2 [..., 전달인자n]]]) { 
    문장
}   

4 조건문
 - if : if문은 조건에 따라 문장을 제어할 수 있는 제어문이다.   
ex) if (username == null) username = "John Doe";   
 - else if : 둘 중 하나가 아닌 여러 개 중 하나의 코드를 실행할 수 있도록하는 제어문이다.   
ex) if (expression) statement1 else statement2
 - switch : 하나의 표현식과 코드 블록으로 구성된 제어문이다.  
ex) switch(n) {
    case 1:
    break;
    case 2:
    break;
    case 3:
    break;
    default:
    break;
}

5 루프
 - while : 기본적인 루프문   
ex) while (표현식) 문장
 - do/while : while과는 다르게 표현식에 관계없이 먼저 한번 실행이 된다.   
ex) do 문장 while (표현식)
 - for : 특정 패턴을 따르는 루프문   
ex) for(초기화; 테스트; 증감) 문장
 - for/in : 객체 내에서 차례대로 변수를 할당해주는 루프문   
ex) for(변수 in 객체) 문장

6 점프문
 - 레이블 : 어떤 문장에라도 그 앞에 식별자 이름과 콜론(:)으 넣음으로써 레이블을 붙일 수 있다.   
ex) mainloop: while(표현식) 문장
 - break : break문을 감싸고 있는 가장 안쪽의 루프를 즉시 빠져나온다.   
ex) for(var i = 0; i < a.length; i++) { if(a[i] == target) break; }
 - continue : break문과 유사하지만 루프를 즉시 빠져나오지 않고 다음 반복을 시작한다.   
ex) for(var i = 0; i < a.length; i++) { if(a[i] == target) countinue; }
 - return : 함수에서 반환하는 값을 지정하는 데 쓰인다.   
ex) return 표현식;
 - throw : 예외를 발생시키는 것   
ex) throw 표현식;
 - try/catch/finally : 자바스크립트의 예외 처리 기법   
ex) try { 예외가 발생할지도 모르는 코드 블록 정의 } catch { try문에서 예외가 발생한 경우 실행(예외 처리) } fanally { 항상 실행이 보장되는 문장 }

7 기타
 - with : 유효범위 체인을 임시로 확장할 때 사용된다.   
ex) with(객체) 문장
 - debugger : 평소에는 아무것도 하지않고, 코드 디버깅 중에 코드의 중단점 역할을 한다.   
ex) function f(o) { if(o === undefined) debugger; }
 - "use strict" : "use strict" 지시어 다음에 오는 코드들이 엄격모드를 따르게 하기 위해 사용된다.   
ex) var hasStricMode = (function() { "use strict"; return this === undefined }());

8. 자바스크립트 문장 요약

|문|문법|용도|
|--------|--------|--------|
|break|break [레이블];|가장 안쪽으 루프, switch문 또는 '레이블'로 명명된 문장 바깥으로 빠져나온다.|
|case|case 표현식:|swich문 내부 문장에 레이블으 붙인다.|
|continue|continue [레이블];|가장 안쪽의 루프, 또는 '레이블'로 명명된 루프를 재시작한다.|
|debugger|debugger;|디버거 중단점|
|default|default:|switch문에서 디폴트 문장에 레이블을 붙인다.|
|do/while|do 구문 while(표현식);|while 루프를 만드는 다른 방법|
|empty|;|아무 일도 안함|
|for|for(초기화; 테스트; 증감) 문장|편리하게 쓸 수 있는 루프|
|for/in|for(변수 in 객체) 문장|객체에 속하 프로퍼티들을 열거한다.|
|function|function 이름([전달인자[,...]]) { 문장 }|'이름'이라는 함수를 선언한다.|
|if/else|if(표현식) 문장1 [else 문장2]|문장1 또는 문장2를 실행한다.|
|label|레이블 : 문장|'문장'에 '레이블'이라는 이름을 붙인다.|
|return|return [표현식];|함수에서 값을 반환한다.|
|switch|switch(표현식) { 문장 }|case 또는 default: 레이블이 붙은 문장들로 다중 분기|
|throw|throw 표현식;|예외를 발생시킨다.|
|try|try { 문장 } [catch(식별자) { 문장 } ] [finally { 문장 } ]|예외르 잡아낸다.|
|use strict|'use strict';|스크립트나 함수르 엄격한 모드로 제한시킨다.|
|var|var 이름 [= 값] [,...];|하나 이상 변수으 선언고 초기화|
|while|while(표현식) 문장|기본적인 루프 생성문|
|with|with(객체) 문장|유효범위 체인의 확장(엄격한 모드에서 사용할 수 없음)|
