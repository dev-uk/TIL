## JavaScript bad case

### bad case
java script 를 작성하면서 :thumbsup:좋은 방법, :thumbsup:좋은 습관이나,:thumbsdown:나쁜 습관, :thumbsdown:나쁜 방법들을 정리

### :black_medium_small_square: 변수 없이 선언
:thumbsdown:
```
  //변수형 var 나 let 없이도 생성이 된다.
  num = 5;
  
  alert(num); //5
```
:thumbsup:
```
  let num = 5;
  
  alert(num); //5
```
<br>
이는 전역변수로 생성되어 좋지 않은 영향을 미칠 수 있다. 이는 use strict 모드에서는 에러로 간주한다.  

https://ko.javascript.info/variables

<br>

### :black_medium_small_square: 변수명명규칙
:thumbsdown:
```
  let a = 1;
  let b = 2;
  let c = a + b;
```
:thumbsup:
```
  let firstNum = 1;
  let secondNum = 2;
  let sum = num1 + num2;
```

명확하지 않은 줄임말, a b c 등은 물론이고 data , value 같은 이름은 아무것도 설명해주지 않는다

코드 문맥상 변수가 가르키는 데이터나 값이 명확할 때에만 사용한다.  

https://ko.javascript.info/variables   


### :black_medium_small_square: 함수는 동작 하나만 담당해야한다.  

함수는 함수 이름에 언급되어있는 동작만을 정확히 수행해야 하며, 그 이외의 동작은 수행해선 안 된다.

`getAge` 함수는 나이를 얻어오는 동작만 수행 해야함.  
`alert`창에 나이를 출력해주는 동작은 이 함수에 들어가지 않는 것이 좋음.  


:thumbsdown:
```
function showPrimes(n) {
  nextPrime: for (let i = 2; i < n; i++) {

    for (let j = 2; j < i; j++) {
      if (i % j == 0) continue nextPrime;
    }

    alert( i ); // 소수
  }
}
```  
소수를 보여주는 `alert` 역할 외의 소수를 판별 하는 동작을 하고있다.  

:thumbsup:
```
function showPrimes(n) {

  for (let i = 2; i < n; i++) {
    if (!isPrime(i)) continue;

    alert(i);  // a prime
  }
}

function isPrime(n) {
  for (let i = 2; i < n; i++) {
    if ( n % i == 0) return false;
  }
  return true;
}
```  
소수를 판별 하는 `isPrime` 함수와 소수를 보여주는 `showPrimes` 역할을 잘 분류하였다.  
위와 같이 작성시 코드의 재사용성을 높이고 코드가 정돈되어 가독성이 높아진다.  

https://ko.javascript.info/function-basics


### :black_medium_small_square: 내용이 긴 문자열

가로로 길게 늘어진 문자열은 백틱(`)을 사용하여 여러줄로 나누자.   
:thumbsdown:
```
  let str = ECMA International's TC39 is a group of JavaScript developers,
implementers, academics, and more, collaborating with the community
  to maintain and evolve the definition of JavaScript.
```   
:thumbsup:
```
  let str = `
  ECMA International's TC39 is a group of JavaScript developers,
  implementers, academics, and more, collaborating with the community
  to maintain and evolve the definition of JavaScript.  
  `;
```

### :black_medium_small_square: 중첩 레벨 최소화
가능하면 깊은 중첩문은 피하는게 좋다.

`continue`, `return` 등 으로 중첩 레벨을 줄여 코드의 가독성을 향상 시키자.

:thumbsdown:
```
function pow(x, n) {
  if (n < 0) {
    alert("'n'은 음수가 될 수 없습니다.");
  } else {
    let result = 1;

    for (let i = 0; i < n; i++) {
      result *= x;
    }

    return result;
  }
}
```

:thumbsup:
```
function pow(x, n) {
  if (n < 0) {
    alert("'n'은 음수가 될 수 없습니다.");
    return;
  }

  let result = 1;

  for (let i = 0; i < n; i++) {
    result *= x;
  }

  return result;
}
```
위의 두가지 코드는 동일하게 동작한다.   
`if`문에서 조건을 확인후 `return` 하거나 부합하지 않으면 중첩 레벨에 속하지 않고 주요 로직으로 넘어가도록 하여 가독성이 좋다.

### :black_medium_small_square: 주석 작성법

좋은 코드에는 설명이 많은 주석이 많아서는 안된다.
코드에서 무슨일이 일어나는지...등

:thumbsdown:
```
  // (...)와 (...)등을 수행...
```


함수는 주석이 없어도 그 존재 자체가 무슨 역할을 하는지 이름으로서 설명해야 한다.   
이는 **자기 설명적인 코드** 라고 한다.   
:thumbsup:
```
function showPrimes(n){...}
function isPrime(){...}
```

#### 함수 용례와 매개변수 정보를 담고 있는 주석

`JSDoc`을 사용해서 함수에 관한 문서를 쉽게 작성할 수 있다.
:thumbsup:
```
/**
 * x를 n번 곱한 수를 반환함
 *
 * @param {number} x 거듭제곱할 숫자
 * @param {number} n 곱할 횟수, 반드시 자연수여야 함
 * @return {number} x의 n 거듭제곱을 반환함
 */
function pow(x, n) {
  ...
}
```

###   :black_medium_small_square:  연산 순서

`or(||)` 와 `and(&&)` 연산할 때 순서가 중요하다.

:thumbsup:
```
  const value1 = true;
  const value2 = false;
  
  /* or */
  if(value1 || value2 || check()){...}

```

`or` 연산은 한가지라도 `true` 면 실행하여 뒤에 연산 하지 않으므로, 가벼운 로직이면서 true인 빈도가 높은 연산을 먼저 실행한다.

`check()` 같이 무거운 연산을 하는 함수를 제일 뒤에서 체크하도록 한다.

:thumbsup:
```
  const value1 = true;
  const value2 = false;
  
  /* and */
  if(value2 && value1 && check()){...}

```
`and`연산은 한가지라도 `false`면 실행하지 않는 논리 연산자이므로, 역시 `false` 빈도가 높은 연산을 먼저 실행하도록 배치 한다.

마찬가지로 `check()` 같은 무거운 연산을 하는 함수를 제일 뒤에서 체크하도록 한다.



### :black_medium_small_square:  Early return, early exit   

:thumbsdown:
```
  function upgradeUser(user){
    if(user.point > 10){
      ...// upgrade logic...
    }
    ...
  }
```

조건을 여러번 체크할때에는 먼저 false인 경우를 체크하여 빠르게 `return` 하도록 한다.

:thumbsup:
```
  function upgradeUser(user){
    if(user.point <= 10){
      return;
    }
    ...// upgrade logic
  }
```