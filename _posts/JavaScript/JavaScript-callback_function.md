# 콜백 함수

## 콜백 함수란 ?
`callback function` 이란 function 안에서 특정 시점에 호출되는 함수이다.   
 보통 `callback function`은 함수의 매개변수로 전달하여 특정 시점에서 콜백 함수를 호출한다.

### 함수 정의
```
function plus(a, b, callback){
    let = sum a + b;
    callback(sum);
}
```

plus function은 인자 a, b와 `callback function`인 callback을 받아 실행하고 있다.

### 정의한 함수 호출
```
plus(10,20,function(result){
    console.log(result);
})
```

`callback function`을 익명 함수로 전달하고 있다. 익명 함수는 result를 받아 log를 찍는다.    
정의된 `plus` 함수에서는 a = 10 , b = 20을 받아 익명 함수를 호출함으로 결과 값으로 30을 console에 출력한다.

**결과**
> 30

### 정의된 함수를 인자로 전달

```
//함수 선언문
function print(result){
    console.log(result);
}

//함수 표현식
const print = function(result){
    console.log(result);
} 
...

plus(10,20,print);
```
미리 정의된 함수도 `callback function`으로 사용 할 수 있다.

## 콜백 함수를 사용했던 예시

이미 `jQuery`나 `ajax`를 사용하면서 `callback function`을 자신도 모르게 많이 사용하였다.

### jQuery에서 사용예시
```
$("button").click(function(){
    alert("버튼 클릭!!!");
});
```
`button` 의 click 이벤트가 발생시 익명 함수를 전달받아 `callback function`을 실행 한다.

### ajax에서 사용예시
```
$.ajax({
    url : "URL",
    type: "GET",
    success: function(){
        //콜백 함수
    },
    error: function(){
        //콜백 함수
    },
    complet: function(){
        //콜백 함수
    }
});
```
`ajax` 통신이 성공,실패,완료시 각각 `callback function`을 실행 한다.









### reference
https://webcoding.tistory.com/entry/JavaScript-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%BD%9C%EB%B0%B1%ED%95%A8%EC%88%98%EB%9E%80   

https://beomy.tistory.com/10