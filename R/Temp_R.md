# R

## command

`100:130` - 100부터 130까지의 수열을 만들어줌
```
 [1] 100 101 102 103 104 105 106 107 108 109 110 111 112 113 114 115 116
[18] 117 118 119 120 121 122 123 124 125 126 127 128 129 130
```
* 위 수열은 변수에 저장이 가능하다.  
`temp = 100:130`  
* 위 수열은 사칙연산이 가능하다  
모든 원소에 대해서 연산이 진행됨.
```
temp - 1
  > [1] 99 100 101 ... (중략)
temp / 10
  > [1] 10 10.1 10.2 ...
temp * 2
  > [1] 200 202 204 ...
temp + 1
  > [1] 101 102 103 ...
```
* 또한 벡터 객체 끼리도 연산이 가능
```
temp + temp
  > [1] 200 202 204 ...
```
* 벡터 리사이클링: A 벡터와 B 벡터가 서로 배수 관계라면 더 작은 벡터가 큰 벡터에 맞게 원소 수가 일정하게 증가
```
A = 1:6
B = 1:2
A + B    # 벡터 리사이클링
  > [1] 2 4 4 6 6 8
  > [1] (1+1) (2+2) (3+1) (4+2) (5+1) (6+2)
```


`Ctlr + C` - 실행 중인 코드 중단  

* 벡터: R에서 벡터란 숫자들의 1차원 집합을 의미  

* R 변수 규칙  
    * 첫 문자로 특수기호 포함 불가
    * 첫 문자로 숫자 포함 불가  
    * 소문자/대문자 구분 가능
        * `name =/= Name`  

`ls()` - 위 함수는 현재 사용 중인 변수(객체)이름을 확인할 수 있음.

* 벡터의 행렬연산  
`die %*% die` - 각 원소의 곱의 전체 합 (내적)  
`die %o% die` - 각 원소의 모든 곱의 경우의 수를 출력 (외적)  

___
## 기본 내장 함수

* `round(A,num)` - A 변수를 num 자리수 만큼 반올림  
(python의 round 함수와 동일)
* `factorial(A)` - A! (팩토리얼)  
* `mean(A:B)` - A:B 벡터 객체의 평균값
    * `round(mean(T))` - 이런식의 사용도 가능
* `sample(x, size, replace = FALSE, prob = NULL)` - x 변수에서 size값 만큼의 갯수를 출력해줌
    * replace 파라미터가 False일 경우 - 비복원 표본 추출 / True일 경우 복원 표본 추출
    * prob - 각 원소별 가중치를 더하는 값  
    ex) `  dice = sample(1:6, 2, TRUE, prob = c(1/8,1/8,1/8,1/8,1/8,3/8))`
    각 원소별로 대치되며 6의 빈도수가 다른 숫자의 빈도수보다 더 많이 출력됨

* `args(function)` - function에 대한 파라미터 출력

* `?function` - function에 대한 함수 설명을 출력 (기본 내장함수에 대해서만 출력)  

* `is.vector(var)` - var 가 vector 객체 유무를 반환

* `length(var)` - var의 길이를 반환

* `now = Sys.time()` - R 내장된 로컬 컴퓨터의 현재 시간 반환
___
## 함수 생성
* 함수의 return 값은 코드의 가장 마지막줄이 된다.  
별도로 return을 입력해줄 필요 없다  
<br>

parameter가 없는 함수
```
my_function = function() {
    die = 1:6
    dice = sample(die, 2, TRUE)
    sum(dice)
}

my_function()
[1] 9
```
  
parameter가 없는 함수
```
my_function = function(param) {
    dice = sample(param, 2, TRUE)
    sum(dice)
}

my_function()
[1] 9
```

parameter의 default가 설정된 함수
```
my_function = function(param  = 1:6) {
    dice = sample(param, 2, TRUE)
    sum(dice)
}

my_function()
[1] 9
```
___
## 패키지 (python의 pip)

* 설치 명렁어  
`install.packages("package_name")`

* 실행 명령어 (python의 import)  
`library("package_name")`


### qplot
* scatter plot
`qplot(x_data, y_data)`  
x_data가 x축 y_data가 y축이 된다.

* histogram  
`qplot(x, binwidth = 1)`  
x 벡터 값의 갯수를 y 축에 표기

* tip  
[1,3] - 1~3  
[1,3) - 1~2  
(1,3] - 2~3  
(1,3) - 2  


___
## 객체
1. atomic Vector  
    * temp_vector = 1:6
    * temp_c = c(1,2,3,4,5,6)
    * 실수, 정수, 문자, 논리, 복소수, 원시형 6가지 자료형의 원자벡터가 있다.

    * 숫자 옆에 L을 입력하면 정수형 벡터 생성  
    `int = 100L`
    * 쌍따옴표로 묶으면 문자형 벡터 생성  
    `text = "temp"`
    * R에서는 기본적으로 숫자는 실수형(double)로 저장한다
    * R은 복소수를 표기할 수 있다 `1+1i`
    * `raw(n)` 함수를 쓰면 길이가 n인 원시형 벡터를 만들 수 있다  
    > raw(3)  
    > [1] 00 00 00



2. 
    
3. 
___
## 반복문 (replicate)
* 기본식  
`replicate(i, function())`  
function() 함수 및 식을 i번 반복한다

___

## 속성
1. 이름
```
> names(die) = c("one", "two", "trhee", "four", "five", "six")
> names(die)
[1] "one"   "two"   "trhee" "four"  "five"  "six"  
> die
  one   two trhee  four  five   six 
    1     2     3     4     5     6 
```

2. 차원  
* 일반 행렬
```
> die = 1:6
> dim(die) = c(2,3)
> die
     [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6
```
* 하이퍼 큐브
    * 핵심은 `dim(die) = c(a,b,c)`에서  
a는 행  
b는 열  
c는 슬라이스
```
> dim(die) = c(1,2,3)
> die
, , 1

     [,1] [,2]
[1,]    1    2

, , 2

     [,1] [,2]
[1,]    3    4

, , 3

     [,1] [,2]
[1,]    5    6
```
___
## 행렬
* 아래와 같이 `matrix(var, ncol or nrow, byrow = TRUE or FLASE)`함수를 사용하면  
행렬을 만들 수 있다
```
> die = 1:6
> m = matrix(die, nrow=2)
> m
     [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6


> m = matrix(die, ncol=2)
> m
     [,1] [,2]
[1,]    1    4
[2,]    2    5
[3,]    3    6


> m = matrix(die, nrow=2, byrow = TRUE)
> m
     [,1] [,2] [,3]
[1,]    1    2    3
[2,]    4    5    6
```
___
## 배열
* 아래는 array 함수를 사용하여 세가지 벡터 객체를 만들어서 묶은 뒤 dim 파라미터로 2x2x3 차원 행렬로 선언해주는 코드
```
> ar = array(c(11:14,21:24,31:34), dim = c(2,2,3))
>
> ar
, , 1

     [,1] [,2]
[1,]   11   13
[2,]   12   14

, , 2

     [,1] [,2]
[1,]   21   23
[2,]   22   24

, , 3

     [,1] [,2]
[1,]   31   33
[2,]   32   34
```
___
## 클래스
* class 함수는 객체의 원자 자료형에 따라 값을 반환  
```
> class("hello")
[1] "character"

> class(5)
[1] "numeric"
```

### factor (R class 중 하나)
* 연구에서 처리 수준이나 다른 범주형 변수를 기록할때 유용하게 사용 됨

```
> gender = factor(c("male","female","female","male"))

> gender
[1] male   female female male  
Levels: female male
```
___
## 리스트
* 타 객체에서는 서로 다른 자료형의 원자벡터를 선언할 경우 하나의 자료형으로 강제변환 되지만  
리스트는 서로 다른 자료형을 한 객체로 묶을 수 있다.
```
> list1 = list(100:130, "R", list(TRUE,FALSE))
> list1
[[1]]
 [1] 100 101 102 103 104 105 106 107 108 109 110 111 112
[14] 113 114 115 116 117 118 119 120 121 122 123 124 125
[27] 126 127 128 129 130

[[2]]
[1] "R"

[[3]]
[[3]][[1]]
[1] TRUE

[[3]][[2]]
[1] FALSE
```
위 코드를 보면 list 객체는 실수형, 문자형뿐만 아니라 자신과 똑같은 list형 객체도 포함할 수 있다.  

___

## 기타

* R에서 한 벡터 안에 서로 다른 자료형의 데이터를 입력하더라도 강제로 한가지 자료형으로 변환 시킨다.
