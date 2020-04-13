# TIL 규칙

개념등 정리하는 저장소.  
규칙을 정의함으로서 작성 방식에 대해 고민하지 않도록 한다.  

index



## 1. 파일 규칙
  
- _posts 폴더 아래 대분류(스킬등), 아래에 스킬명-주제.md 파일로 작성
    > ex) _posts/JavaScript/JavaScript-function.md

- 이 파일은 포스팅 파일이라 칭함.

- 포스팅 제목에 띄어쓰기가 있을 경우 언더바(_)로 작성.
    > ex) JavaScript-strict_mode.md

- 각 대분류는 index.md 파일을 가지며, 이곳엔 포스팅 리스트를 작성한다

- resource 파일은 대분류 폴더 안에 위치하도록 한다
    > ex) CSS/image/...

## 2. 작성 규칙

### 2-1. 대분류 index.md 파일

  [index template](indexTemplate.md)

- 최상단에 대분류 명 h1(`#`) 으로 작성
    > ex) # JavaScript

- 포스팅 리스트를 목록(`-`) 으로 작성하고 md 파일 링크를 삽입한다.
    > ex) - `[JavaScript-엄격모드](_posts/JavaScript/JavaScript-strict_mode.md)`   


### 2-2. 포스팅 파일

[post template](postTemplate.md)

- 최상단에 포스팅 타이틀 h1(`#`) 으로 작성
    > ex) # JavaScript-function



- 최하단에 참조 페이지 링크 h3(`###`) 으로 작성
- 




