## strict mode

### strict mode란?

ES5에 추가된 키워드다. JavaScript는 어느정도 에러를 무시하고 넘어가서 버그를 유발할 수 있다.
안전한 코딩을 위한 하나의 가이드 라인으로서, 문법을 엄격하게 검사하겠다 라는 뜻이다.

### strict mode 선언

script 시작 또는 함수 부분에 'use strict' 라고 선언한다
실수를 에러로 변환시켜 차후 일어날 수 있는 버그를 방지 한다.

> 전역 컨텍스트에 선언하여 모든 코드에 strict mode를 적용함
```
<script>
  'use strict'
   ...
</script>
```

> 함수 내에 선언하여 함수의 모든 코드에 strict mode를 적용함
```
  function strict(){
    "use strict"
    ...
  }
```

### strict mode 적용 예시

> eval 이라는 변수명을 사용할 수 없게함

![test](/_resource/image/JavaScript/JavaScript-strict_mode-01.PNG)



### reference
https://blog.aliencube.org/ko/2014/01/02/reasons-behind-using-strict-mode-while-coding-javascript/

https://ko.javascript.info/strict-mode

https://beomy.tistory.com/13
