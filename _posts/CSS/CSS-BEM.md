## CSS BEM

### BEM 이란?   
CSS Architecture.로 개발 방법론.   
`Block`__`Element`--`Modify` 형식으로 CSS 의 class 이름을 작성하여 읽고 이해하고 확장하기 쉽도록 한다.

- `block` : 구성 요소의 가장 바깥 쪽 부모 요소를 정의
- `Element` : 구성 요소의 내부에 위치
- `Modify` : `block` 또는 `Element`의 속성으로 스타일 정의
  

### 예제1. block , block--modify
   :thumbsdown:
```
    <button class="btn"></button>

    <button class="btn btn--red">

    <style>
        // block 레벨의 스타일만 작성
        .btn{
            display : inlin-block;
            color : blue;
        }

        //블록의 스타일만 작성
        .btn--red{
            color : red;
        }
    </style>
```

:thumbsdown: `modify`를 단독으로 사용 하지 않는다.

```
    <button class="btn--red"></button>

    <style>
        .btn--red{
            display: inline-block;
            color: red;
        }
    </style>
```
`block`에 지정해야할 스타일을 작성함으로 확장성 및 재활용성을 떨어뜨린다.


### reference
https://velog.io/@yesdoing/BEM-Block-Element-Modifier-Quick-start   

https://seesparkbox.com/foundry/bem_by_example   

https://sh-sida.tistory.com/34