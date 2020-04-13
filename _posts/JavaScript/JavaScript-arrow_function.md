# 화살표 함수

화살표 함수(arrow function)은 단순하고 간결한 문법으로 함수를 만들 수 있다.   
이 화살표 함수는 `ES6` 의 문법이다.

## 화살표 함수 문법

```
// 화살표 함수
let sum = (a,b) => a + b;

// 이 함수는 위의 함수와 같다.
let sum = function(a,b){
  return a + b;
}

```
- `(a,b)` 에는 함수가 받을 인자값을 설정한다
- 화살표 `=>`의 우측은 return 받을 표현식을 작성한다 

a, b를 받아 a + b 를 계산 한 값을 리턴한다

- 인수가 하나뿐일때는 괄호를 생략 가능하다   
```
let double = n => n * 2;
```

</br>

- 인수가 없을경우 괄호만 작성한다. **괄호는 필수**   

```
let hello = () => alert("hello");
```
</br>

- 함수 본문이 여러줄인 경우 `{...}` 중괄호로 묶는다.

```
let sum = (a,b) => {
  let result = a + b;
  return result;
}
```   
중괄호로 묶은경우 명시적으로 `return` 을 사용하여 결과값을 반환해야 한다. 




### reference

https://ko.javascript.info/arrow-functions-basics   

