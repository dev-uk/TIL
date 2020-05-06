# JavaScript Class

## 클래스란?
객체(Object)를 만들기 위한 틀(template)로 JavaScript에선 **ES6**에 추가되었다.

기존에 존재하던 `prototype`을 기반으로 설계되었다.


## 클래스 선언
```
class Person{
    
    //생성자
    constructor(name, age){
        //fields
        this.name = name;
        this.age = age;
    }

    // methods
    speak(){
        console.log(`${this.name}: hello!`);
    }
}
```

## 클래스로 객체(Object)생성
```
const byeonguk = new Person("byeonguk",20);

console.log(byeonguk.name);
console.log(byeonguk.age);
byeonguk.speak();
```

**결과**
> byeonguk   
> 20   
> byeonguk: hello! 

## Getter and Setter
```
class Person{
    
    //생성자
    constructor(name, age){
        //fields
        this.name = name;
        this.age = age;
    }
    
}
```
위와 같은 클래스가 있다. 그 안에 getter 메소드와 setter 메소드를 만든다.

```
get age(){
    return this.age;
}
set age(value){
    this.age = value;
}

```
위와 같이 getter 와 setter를 만들고 객체를 생성하면   
 **Uncaught RangeError: Maximum call stack size exceeded**    에러가 발생할 수 있다.

생성자안의 `this.age`는 `getter`를 호출한다.

또 `this.age`에 `age` 할당하기 위해 `setter`를 호출한다.

이는 `setter`안에서 `this.age`에 값을 할당하기 위해 `setter`인 자신을 무한호출함으로 에러가 발생한다.

이를 해결하기 위해 변수 이름을 다르게 해준다.

```
get age(){
    return this._age;
}

set age(value){
    this._age = value;
}
```