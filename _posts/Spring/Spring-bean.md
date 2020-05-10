# Spring bean 

## bean 이란?

`bean`은 애플리케이션의 핵심을 이루는 객체이다   
`IOC 컨테이너`에 의해 생성, 관리, 인스턴스화 된다.  
설정 메타 데이터(XML) 파일에 의해 정의에 따라 생성된다

## bean XML에 설정하기

일반적으로 bean 정보는 XML 파일에 정의한다.

```
<!-- A simple bean definition -->
<bean id="..." class="..."></bean>

<!-- A bean definition with scope-->
<bean id="..." class="..." scope="singleton"></bean>

<!-- A bean definition with property -->
<bean id="..." class="...">
	<property name="message" value="Hello World!"/>
</bean>

<!-- A bean definition with initialization method -->
<bean id="..." class="..." init-method="..."></bean>

```
### 설정 속성

- `class` : `bean`으로 생성하고자 하는 Java Class   
- `id`    : 고유 식별자
- `scope` : `bean`의 유효 범위   
  - singleton : defalut.
  - prototype 
- `constructor-arg` : 생성자에 전달할 인수
- `property` : 생성시 bean setter에 전달할 인수
  









### reference

https://gmlwjd9405.github.io/2018/11/10/spring-beans.html