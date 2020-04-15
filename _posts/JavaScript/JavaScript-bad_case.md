## JavaScript bad case

### bad case
java script 를 작성하면서 :thumbsup:좋은 방법, :thumbsup:좋은 습관이나,:thumbsdown:나쁜 습관, :thumbsdown:나쁜 방법들을 정리

### 변수 없이 선언
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

### 변수명명규칙
:thumbsdown:
```
  let a = 1;
  let b = 2;
  let c = a + b;
```
:thumbsup:
```
  let num1 = 1;
  let num2 = 2;
  let sum = num1 + num2;
```

명확하지 않은 줄임말, a b c 등은 물론이고 data , value 같은 이름은 아무것도 설명해주지 않는다

코드 문맥상 변수가 가르키는 데이터나 값이 명확할 때에만 사용한다.  

https://ko.javascript.info/variables   


### 함수는 동작 하나만 담당해야한다.  

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


