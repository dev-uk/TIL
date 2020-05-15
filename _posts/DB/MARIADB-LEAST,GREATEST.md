# LEAST , GREATEST 내장함수

해당 함수는 `mysql` , `mariadb`의 내장함수이다.

다수의 값, 컬럼을 비교하여 가장 큰값 및 가장 작은값 구할 수 있다.


## 가장 큰 값 구하기

`GREATEST` 함수를 이용하여 구한다
```
SELECT
  GREATEST(컬럼1, 컬럼2, 값1, 값2 ...)
FROM TABLE;
```

### EX) 

```
SELECT GREATEST(10,20,80,120,1,5) MAX_NUM;
```
**결과**
> MAX_NUM   
> 120

문자열도 비교할 수 있다.

```
SELECT GREATEST('B','c','a') STR;
```

**결과**
> STR   
> B


</BR>   

## 가장 작은 값 구하기

`LEAST` 함수를 이용하여 구한다

```
SELECT
  LEAST(컬럼1, 컬럼2, 컬럼3 ...)
FROM TABLE;
```

### EX)
```
SELECT LEAST(10,20,80,120,1,5) MIN_NUM;
```

**결과**
> MIN_NUM   
> 1

마찬가지로 문자열도 비교할 수 있다.

```
SELECT LEAST('B','c','a') STR;
```

**결과**
> STR   
> a


### reference
https://www.w3schools.com/sql/func_mysql_greatest.asp   
https://www.w3schools.com/sql/func_mysql_least.asp

