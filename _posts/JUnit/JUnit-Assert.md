## JUnit Assert 메소드 정리

JUnit에서 많이 사용되는 메소드로 테스트 케이스의 수행 결과를 판결한다.

### assertEquals(x, y)   
x와 y의 값이 일치하면 통과.   
</br>

### assertNotEquals(x, y)   
x와 y의 값이 일치하지 않으면 통과.   
</br>

### assertArrayEquals(a, b)   
배열 a와 b가 일치하면 통과.   
</br>

### assertFalse(x)   
x가 false 일시 통과.   
</br>

### assertTrue(x)   
x가 ture 일시 통과.   
</br>

### assertNull(x)   
x가 null 일시 통과.   
</br>

### assertNotNull(x)   
x가 null이 아니면 통과.
</br>

### assertSame(x, y)   
x와 y의 같은 객체일시 통과(주소값 동일)   
</br>

### assertNotSame(x, y)
x와 y가 같은 객체가 아닐때 통과   
</br>

### assertThat()
