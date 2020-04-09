## JQuery attr() VS prop()

JQuery 1.6 버전이전엔 `attr()`을 사용하다 checkbox의 버그로 인해 `prop()`을 따로 분류하였다.


### attr() 과 prop() 의 차이

`attr()` : HTML 의 속성(attribute) ==> HTML element 의 값

`prop()` : JavaScript 의 프로퍼티(property) ==> HTML 파싱 후 JavaScript 객체의 프로퍼티 값  
  
  
### 예제

```
  <input id="style" style="font:arial;"/>
```

> .attr() : style 값인 font:arial 리턴.  
> .prop() : CSSStyleDeclaration 객체 리턴.  



### reference  
https://webclub.tistory.com/118  
https://devyj.tistory.com/26
