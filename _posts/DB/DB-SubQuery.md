# 서브쿼리

`maria DB` 기준

## 서브쿼리란?   

하나의 SQL안에 포함되어 있는 또 다른 SQL문  
메인 쿼리가 서브 쿼리를 포함하는 종속적인 관계   
메인 쿼리 안에 괄호() 로 작성한다.   


## 서브쿼리 종류
1. 스칼라 서브쿼리(Scalar Subquery)   
2. 인라인 뷰(Inline view)   
3. 중첩 서브쿼리

SELECT 스칼라 서브쿼리   
FROM 인라인 뷰   
WHERE 중첩 서브쿼리   

### 1. 스칼라 서브쿼리

 - SELECT 문에 작성
 - 하나의 레코드(row) 만 리턴
 - 데이터 건수가 적을 경우 `JOIN` 방식보다 유리

#### 부서 이름을 구하는 예시 쿼리   
`JOIN` 을 이용한 쿼리
```
 SELECT
  EEPTNO, ENAME, EMP.DEPNO, DNAME 
 FROM EMP, DEPT
 WHERE EMP.DEPTNO = DEPT.DEPTNO;

```

`스칼라 서브쿼리`를 이용한 쿼리
```
 SELECT 
  EMPNO, ENAME, DEPTNO, 
  (SELECT DNAME FROM DEPT WHERE EMP.DEPTNO = DEPT.DEPTNO) DNAME
  FROM EMP
```



## 실행 흐름

서브 쿼리 수행 => 메인 쿼리 수행 
