## Spring DataSource

### DataSource란?   
`DataSource`는 `Connection Pool`을 관리하는 목적의 객체. [`Connection Pool`이란?](/_posts/DB/DB-connection_pool.md)   
`DataSource`는 서버에서 관리 하기 때문에 DB정보나 JDBC 드라이버 정보가 변경되더라도 application을 변경할 필요 없다. (application과 DB작업의 분리) 
