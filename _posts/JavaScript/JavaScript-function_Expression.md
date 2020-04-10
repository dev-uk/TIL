## JavaScript 함수 표현식

함수도 값이다 다른 타입처럼 할당,표현,복사 할 수 있다.

### 함수 표현식 VS 함수 선언문

- 함수 선언문  
```
  function hello(){
    alert("hello function!);
  }
```

- 함수 표현식  
```
  let hello = function (){
    alert("hello function!);
  }
```

#### 차이점  
1. 자바스크립트 엔진에 의해 함수가 생성되는 시점  

함수 표현식 : 실제 실행 흐름이 코드에 도달 했을때 생성. 즉 **런타임 환경**에 생성. 
</br></br>
함수 선언문 : 함수 선언문이 정의가 되기전에 사용가능. 따라서 전역 함수선언문은 스크립트 어디에 존재하던 호출가능. 즉 **컴파일 시점**에 생성.(함수 호이스팅)  

> 자바스크립트는 스크립트를 실행하기 전 준비단계에서 전역에 선언된 함수를 찾아 해당 함수를 생성한다. 스크립트가 진짜 실행되기 전 "초기화 단계"에서 함수 선언 방식으로 정의한 함수가 생성되는 것.</br></br>  스크립트는 함수 선언문이 모두 생성된 후 실행된다. 따라서 함수 선언문은 스크립트 어디에 있던 호출이 가능하다. 

```
//함수 선언문

  hello(); /* "hello function!" */

  function hello(){
    alert("hello function!);
  }
```  

```
//함수 표현식

  hello(); /* Uncaught ReferenceError: Cannot access 'hello' before initialization */
  
  let hello = function (){
    alert("hello function!);
  }

```

2. 스코프  

엄격모드('use strict')에서 함수 선언문이 코드블록`{...}`내에 위치하면 블록 내 어디서든 접근이 가능하다. 하지만 코드블록 밖에서는 접근하지 못한다.  
```
  //함수 선언문
  'use strict'
  
  /* 런타임 환경에 생성되는 값 */
  let age = prompt("나이를 알려주세요");
  
  if(age > 19){
    function welcome(){
      alert("안녕하세요");
    }
  }else {
    function welcome(){
      alert("안녕");
    }
  }
  
  //function이 존재하는 코드 블럭 밖에서 호출
  welcome(); /* Error: welcome is not defined */
```

함수 선언문이 포함된 블록 내에서만 유효하기 때문에 밖에서는 접근하지 못한다.

```
  //함수 표현식
  'use strict'

  let age = prompt("나이를 알려주세요.");

  let welcome;                 
  if (age > 19) {

    welcome = function() {
      alert("안녕하세요");
    }

  } else {

    welcome = function() {
      alert("안녕");
    }

  }

  // 정상실행
  welcome();
  
```

`if` 블록 밖에 welcome 을 선언 해줌으로 welcome 함수를 호출 할 수 있다. 


### reference  
https://ko.javascript.info/function-expressions
