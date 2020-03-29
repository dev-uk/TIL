## HTTP request

### HTTP request

HTTP 메세지 중 request는 요청으로써, 클라이언트가 요청에 대한 정보를 담아 서버로 서비스를 요청하는 메세지이다.

### HTTP request header

```
GET / HTTP/1.1
Host: github.com
Connection: keep-alive
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.149 Safari/537.36
Sec-Fetch-Dest: document
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Accept-Encoding: gzip, deflate, br
Accept-Language: ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7
....
```
>github의 페이지 요청중 일부.

GET / HTTP/1.1 은 request Line, 그 이후로는 request header, 통틀어 request Message header이다.
****
#### 시작줄 (GET / HTTP/1.1)
첫번째 줄에 오며, 요청방식인 HTTP method(GET,POST 등) / 요청한 정보(1.html 등) / 사용중인 HTTP버전 (HTTP1.1,HTTP1.0) 등 으로 이루어져 있다.
EX) get 형식으로 background.png 이미지 파일을 요청한다
```
GET / background.png / HTTP 1.1
```

****
#### HOST
서버의 도메인 네임을 보여준다.

****
#### User-Agent
User-Agent 헤더는 사용자의 클라이언트 정보(운영체제, 브라우저 등)를 보여준다.


****
#### Accept

****
#### Accept-Encoding
Accept-Encoding 헤더는 클라이언트가 이해 가능한 컨텐츠 인코딩이 무엇인지 보여준다.
요청에 의해 데이터를 받을때 압축된 데이터를 받는다.
클라이언트가 지원하는 압축 방식을 Accept-Encoding 헤더에 담아 보내주고,
서버는 이 헤더에 맞는 방식으로 응답해준다.
응답된 압축 방식은 Content-Encoding 응답 헤더를 이용해 클라이언트에게 알려준다.


****
#### Authorization

****
#### Origin

****
#### IF-Modified-since


### reference
https://www.youtube.com/watch?v=1TigiIAPipA
https://developer.mozilla.org/ko/docs/Web/HTTP/Messages
https://www.zerocho.com/category/HTTP/post/5b3ba2d0b3dabd001b53b9db
