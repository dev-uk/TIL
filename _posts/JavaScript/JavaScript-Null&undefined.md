# Null 과 undefined

### Null

null은 오로지 null값만 포함하는 별도의 자료형  
자바스크립트의 null은 존재하지 않는 값, 비어 있는 값, 알 수 없는 값을 나타내는 데 사용  
boolean에서는 **false**, Number에서는 **0**의 값을 리턴

### undefined

undefined 값도 오로지 undefined값만 포함하는 자료형을 형성  
undefined는 값이 할당되지 않은 상태를 나타낼 때 사용
선언은 되었지만 값이 할당된 적이 없는 변수에 접근하거나, 존재하지 않는 객체 프로퍼티에 접근할때 반환됨
boolean에서는 **false**, Number에서는 **NaN**의 값을 리턴

### Null와 undefined비교  

동등 연산자 (==)로 비교시엔 ture가 반환된다.
```
null == undefined // true
```

일치 연산자 (===)로 비교시엔 자료형이 다르기에 false가 반환된다.

```
null === undefined // false
```

