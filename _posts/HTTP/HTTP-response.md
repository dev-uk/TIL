
## HTTP response

### HTTP response
HTTP 메세지중 response는 응답으로써, 클라이언트의 요청에 대한 정보를 바탕으로 서버가 응답을 해주는 메세지이다.

### HTTP response Header
```
HTTP/1.1 200 OK
Date: Wed, 25 Mar 2020 15:04:01 GMT
Content-Type: text/html; charset=utf-8
Transfer-Encoding: chunked
Server: GitHub.com
Status: 200 OK
Vary: X-PJAX
ETag: W/"46b423bc8134e56c6524fe456b84d484"
Cache-Control: max-age=0, private, must-revalidate
```
> github의 페이지 응답중 일부.

### 시작줄(상태줄)
```
HTTP/1.1 200 OK
```
상태줄에는 응답의 상태를 보여준다. 프로토콜 버전 / 응답상태코드 를 보여준다

#### 상태코드
| 코드  | 설명 | 
| :--- | ---: |
| 10x     | 정보 |
| 20x     | 성공 |
| 30x     | 리다이렉션 |
| 40x     | 클라이언트 에러 |
| 50x     | 서버 에러|

### Content-Type
서버가 응답할 때 응답의 타입을 보여준다.

### Content-Encoding
해당 컨텐츠의 압축 방식.

### Content-Disposition

### Allow

