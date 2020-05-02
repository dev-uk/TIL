# async VS defer

JavaScript 파일을 문서에 포함하는 경우 여러가지 방법으로 포함할 수 있다.

브라우저는 HTML 문서를 위에서 한줄 씩 분석하며 `DOM` 요소로 변환한다.

JS 파일을 포함하는 `<script>` 태그를 만났을 때 어떤식으로 처리하는지 알아보자.

## `<head>`안에 위치 한 경우

```
<head>
    <script src="main.js"></script>
</head>
```

`<head>` 안에 `<script>`를 만나면 HTML을 parsing 하는 것을 멈추고 JS를 다운 및 실행한다.

### 흐름
1. pasing HTML
2. fetching js 
3. executing js 
4. pasing HTML

### 단점
이는 JS 파일의 사이즈가 큰 경우 이를 다운받고 실행할때까지 HTML parsing이 진행되지 않아 페이지가 느리게 로딩된다는 단점이 있다.   

</br>   

## `<body>`안에 위치 한 경우

```
<body>
    ...
    <script src="main.js"> 
</body>
```

body 제일 하단에 위치한 경우. HTML pasing이 끝난 후 이므로 페이지가 로딩 된 후 JS 파일을 다운받는다.

### 흐름
1. parsing HTML
2. parsing을 멈추고 JS파일 다운로드 
3. JS 파일 실행

### 단점
문서가 JS 파일에 의해 데이터를 받아오거나, `DOM`요소를 꾸며주는 등 의존적인 경우 정상적인 페이지를 이용하기까지는 JS 파일의 다운 및 실행을 기다려야 한다.



### `<head>` + `async`

```
<head>
    <script asyn src="main.js"></script>
</head>
```

`async`는 boolean 타입으로 선언시 **true**로 설정

### 흐름
1. parsing HTML   
2. parsing 을 진행하며 JS 파일  **병렬** 다운로드   
3. 다운완료 시 parsing 을 멈추고 JS 파일 실행.   
4. parsing HTML

### 여러개의 JS 파일 다운로드 시
JS 파일을 여러개 다운로드 후 먼저 다운로드 된 JS파일을 실행한다.

### 장점
parsing 하면서 JS 파일을 다운 받기 때문에 시간을 절약 할 수 있다.

### 단점
HTML이 전부 parsing 되지 않았기 때문에, JS파일 실행 시점에 생성되지 않은 `DOM`을 조작 하는 행위가 에러가 날 수 있다.

JS파일이 실행되는 동안에는 여전히 HTML 파일을 parsing 하지 않기 때문에 페이지가 로딩되는데 시간이 걸린다.



## `<head>` + defer

### 흐름
1. parsing HTML
2. parsing 을 진행하며 JS 파일 다운로드.
3. parsing이 끝난경우 JS 파일 실행

### 여러개의 JS 파일 다운로드
모든 JS 파일을 다운로드 후 순서대로 실행한다.

### 장점
HTML parsing과 JS 파일 다운로드를 동시에 진행하여 페이지 로딩 시간을 줄여준다.



### reference
https://www.youtube.com/watch?v=tJieVCgGzhs&list=PLv2d7VI9OotQ1F92Jp9Ce7ovHEsuRQB3Y&index=17