## DataBase 커넥션 풀

### Connection pool 이란?

`DB`에 연결하는 일은 많은 자원과 시간이 소요되는 일이다.   
클라이언트의 요청마다 `DB`에 연결한다면 성능적으로, 효율상 문제가 생길 수 있다.
이를 해결하기 위해 `Connection Pool`을 사용한다.  
</br>

`WAS`가 실행 되면서 `DB`에 연결해놓은 객체들을 `Pool`에 담아 두었다가, 클라이언트 요청시 빌려주고 다시 돌려 받는다.


### reference   
https://linked2ev.github.io/spring/2019/08/14/Spring-3-%EC%BB%A4%EB%84%A5%EC%85%98-%ED%92%80%EC%9D%B4%EB%9E%80/   
