## JUnit 어노테이션 정리

해당글은 **JUnit4** 를 기준으로 작성하였다.

### @Test   
`@Test`가 선언된 메소드는 테스트를 수행하는 메소드가 된다.   
```
// 테스트 메소드
@Test
public void testMethod(){
  ...(테스트할 로직)
}
```
### @Test(timeout=ms)   
timeout에 설정된 시간안에 메소드가 수행돼야한다.
```
// 테스트 메소드 시간 제한
/* 해당 메소드는 수행시간이 5초를 넘기면 실패처리 */
@Test(timeout=5000)   
public void testMethod(){
  ...(시간제한 테스트메소드..)
}
```
### @Test(expected=Exception.class)
Exception이 발생해야 하는 메소드   
```
// 테스트 메소드 Exepction 지정
/* 해당 메소드는 Exepction이 발생해야 성공처리*/
@Test(expected=RuntimeException.class)
public void testMethod{
  ...(exception이 발생해야 하는 메소드..)
}
```

### @BeforeClass   
`@Test` 메소드 **이전**에 수행되며, **한 번만** 수행된다.   
```
@BeforeClass
public void beforeClassMethod(){
  ...(@Test 이전 한번만 실행될 로직)
}

```

### @AfterClass
`@Test` 메소드 **이후** 수행되며, **한 번만** 수행된다.

```
@AfterClass
public void afterClassMethod(){
  ...(@Test 이후 한번만 실행될 로직)
}
```

### @Before
`@Test` 메소드 **이전**에 수행되며, **매번** 수행된다.   
`@Test` 메소드 수행에 공통으로 필요한 코드를 작성할 때 사용한다.   
테스트 수행시 매번 설정하는것이 비효율적인 DB설정등을 한 번만 설정하여, 여러 테스트에서 공유하여 사용한다.   
`static`을 붙여 줘야 한다.

```
@Before
public static void beforeMethod(){
  ...(@Test 이전 매번 실행될 로직)
}
```

### @After
`@Test` 메소드 **이후**에 수행되며, **매번** 수행된다.
`@Test` 메소드에서 사용한 자원을 해제할 때 사용한다.
메소드는 `static`이여야 한다.
```
@After
public static void afterMethod(){
  ...(@Test 이후 매번 실행될 로직)
}
```   

### @Ignore   
`@Ignore`가 선언된 메소드는 테스트를 실행하지 않는다.
```
public void ignoreMethod(){
  ...(테스트가 되지 않는 메소드)
}
```

### 호출 순서 보기   
```
@BeforeClass
public static void beforeClassMethod() {
  System.out.println("@BeforeClass");
}

@AfterClass
public static void afterClassMethod() {
  System.out.println("@AfterClass");
}

@Before
public void beforeMethod() {
  System.out.println("@Before");
}

@After
public void afterMethod() {
  System.out.println("@after");
}

@Ignore
public void ignoreMethod() {
  System.out.println("@Ignore");
}

@Test
public void testMethod() {
  System.out.println("@Test");
}
```

#### 출력   
```
@BeforeClass
@Before
@Test
@after
@AfterClass
```    
</br></br></br></br>



### reference   
http://www.nextree.co.kr/p11104/   
https://junit.org/junit4/javadoc/latest/index.html
