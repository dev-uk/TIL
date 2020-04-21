## JavaScript 객체

### 객체란?   
객체는 특수한 기능을 가진 연관성 있는 배열.   
객체는 프로퍼티(property) 키(key)와 값(value)을 저장한다.   

- property key는 문자열이나 심볼이여야 한다. ( 보통은 문자열 )
- 값은 모든 자료형도 가능

### 객체의 프로퍼티에 접근방법   
1. 점 표기법 : `obj.property`   
  `객체.프로퍼티`로 접근
2. 대괄호 표기법 : `obj["property"]`   
  `객체[프로퍼티]`로 접근. `obj[key]`같이 변수를 대입하여 키를 가져올 수 있다.
  

### 객체의 대한 연산자   
- 프로퍼티 삭제 : `delete obj.prop`   
- 객체내에 해당 key 존재 확인 : `"key" in obj`   
- 객체 프로퍼티 나열 : `for (let key in obj)`

### 객체 복사   
객체는 참조에 의해 할당되고 복사된다. 변수에는 `객체`자체가 아닌 객체를 가르키는 메모리상의 주소가 저장된다.   

#### 얕은 복사   
```   
 let user = { 
   name : "uk",
   age : 20
 };
 let cloneUser = user;
```
다음과 `user`를 `cloneUser`에 대입하는 행위는 `얕은복사` 즉 `객체`자체가 아닌 메모리 주소를 대입하는 행위이다.   
해서 `cloneUser의` 프로퍼티를 변경하면 원본인 `user`의 프로퍼티도 변경이 된다.

```
  cloneUser.name = 'byeong uk';
  
  alert(user.name) //'byeong uk';
```

### 깊은 복사   
객체를 참조하는 메모리 주소가 아닌 객체 자체를 복사하는 방법.   
1. 새로운 객체를 생성하고 복사할 객체의 프로퍼티를 순회해 원시 수준까지 프로퍼티를 복사
```
  let cloneUser = {};
  
  // 빈 객체에 프로퍼티를 전부 복사
  for(let key in user){
    cloneUser[key] = user[key];
  }

```
2. Object.assign 사용   
```
  let cloneUser = Object.assign({}, user);
```
  
  
  
  
### reference   
https://ko.javascript.info/object
