## JavaScript bad case

### bad case
java script 를 작성하면서 나쁜 습관이나 나쁜 방법들을 정리

### 변수 없이 선언

<br>

```

  //변수형 var 나 let 없이도 생성이 된다.
  num = 5;
  
  alert(num); //5
  
```

<br>
이는 전역변수로 생성되어 좋지 않은 영향을 미칠 수 있다. 이는 use strict 모드에서는 에러로 간주한다.  


https://ko.javascript.info/variables

<br>

### 변수명명규칙

명확하지 않은 줄임말, a b c 등은 물론이고 data , value 같은 이름은 아무것도 설명해주지 않는다

코드 문맥상 변수가 가르키는 데이터나 값이 명확할 때에만 사용한다.  

https://ko.javascript.info/variables
