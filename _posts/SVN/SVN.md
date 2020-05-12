# SVN

## SVN 이란?

소프트웨어 형상관리(버전관리) 툴. 소스를 버전별로 관리한다.

## 용어

- `Repository` : 저장소로 모든 프로젝트의 소스들이 저장된 곳. 소스 변경 사항도 저장됨.
- `trunk` : 프로젝트의 중심이 되는 디렉토리.
- `branches` : `trunk` 에서 뻗어나온 가지를 뜻하며, 프로젝트 내의 작은 프로젝트
- `Revision` : 소스 파일을 수정하여 `commit`

## 명령어   
- `import` : 저장소에 새로 프로젝트 등록하는 명령어
- `Check out` : `Repository`에서 소스를 받아오는 명령어.
- `commit` : `Check out` 후 변경한 소스를 `Repository`에 갱신
- `update` : `Repository`의 최신 소스로 업데이트 하는 명령어.
