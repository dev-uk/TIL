# 클로저(closure)

## 클로저란?

생명주기가 끝난 외부 함수의 변수를 내부함수가 참조할 수 있는것이 클로저라 한다.

```
function outter(){
    var name = 'outter function name';
    function inner(){
        alert(name);
    }
}
```
외부함수인 `outter`는 `name` 변수와
내부함수인 `inner`함수를 가지고있다.

내부함수인 `inner`는 외부함수인 `outter`의 변수인 `name`에 접근할 수 있다.

