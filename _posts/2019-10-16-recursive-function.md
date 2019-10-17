---
layout: post
title: 'recursive function - 재귀함수'
date: 2019-10-16 23:00
categories: [language, python]
# os, windows, linux, 
# service, github
# language, python, c
# etc, blog, jekyll
---

# recursive function - 재귀함수

## 설명을 읽고 재귀함수에 대해 이해하기
재귀함수의 의미, 장단점, 필요성, 주로 사용하는 문제를 정리한다.
프로그램 언어를 배울 때 꼭 설명하는 알고리즘 형태다. 학교에서 배울 때 시험문제에 자주 나오기도 한다. 실전에서는 속도 문제도 있고 이해하기 어려울 때가 있어서 많이 사용하지는 않는다. 최근 함수형 프로그램이 주목을 받으면서 함수형 프로그램에 필요한 재귀함수 작성법을 일부러 배우기도 한다.

[나무위키-재귀함수](https://namu.wiki/w/%EC%9E%AC%EA%B7%80%ED%95%A8%EC%88%98)
* 절차형 프로그램보다는 함수형 프로그램에서 사용한다.
* 반복문으로 구현하기 어려운 알고리즘을 쉽게 구현한다.
* 파이썬은 함수 깊이 제한이 있다. 꼬리재귀 최적화 지원하지 않는다.
* 재귀함수는 C로 짜라

[wikipedia-Recursion (Computer science)](https://en.wikipedia.org/wiki/Recursion_(computer_science))
* 시간나면 천천히 읽어보기로 하고

## 생각해 볼 문제
재귀함수는 알고리즘을 구현한 형태로 이해하기 쉬운 경우가 있다. 반대로 알고리즘을 이해하지 못하면 반복문보다 구현하기 어려운 점도 있다. 반복문을 사용할 것인가? 재귀함수를 사용할 것인가? 생각해 볼 문제는 무엇인가?
* 알고리즘이 명확한가? 이해하기 쉬운가?
* 메모리 사용 - stack
* 속도 - 반복호출, memoization
* 종료 조건

#### factorial
factorial은 1부터 입력받은 숫자까지 모두 곱한 값이다. 일반적으로 for 문으로 쉽게 작성할 수 있다.
또한 함수 f(x)로 표현하기 쉽고 구현하기가 쉬워서 재귀함수의 좋은 예가 된다.
* n! = 1 x 2 x 3 x ... x n-1 * n

**반복문 사용**
```python
def factorial_calc(num):
result = 1
for i in range(1, num+1):
    result *= i
return result
```

**재귀함수 사용**
```python
def factorial_recursive(num):
  if num == 1:
    return 1
  return num * factorial_recursive(num-1)
```

실제 작성하고 동작시켜 보고 알게 된 생각해 볼 점
* factorial은 결과값이 매우 크기 때문에 두 함수의 성능차이를 측정할만큼 큰 수를 입력하기 어려울 것으로 예상한다.
* 결과값의 오버플로우보다 깊이 제한에 먼저 걸린다. 500을 입력하면 maximum 'RecursionError: recursion depth exeeded'가 발생한다.
* 반복문은 함수호출 1번, 재귀함수는 num 만큼 함수를 호출한다
* 성능차이는 9배 정도 반복문이 빠르다.(시스템 성능에 따라 다를 듯)

#### fibonacci
피보나치 수열은 앞의 두 숫자를 더해서 다음의 숫자를 구하는 수열이다.
```몇 달 후의 토끼는 몇 마리인가?``` 문제 형태로 나온다. 대표적인 알고리즘 문제고 재귀함수를 설명하기 좋은 예다.
* n = n-2 + n-1
* n[0]=0, n[1]=1 - 알고리즘 상으로는 ```n[0] = 1``` 로 시작할 수 있다.

**반복문 사용**

```python
def fibonacci_calc(num):
  if num < 2:
    return num

  n1 = 1
  n2 = 1
  result = 0
  for i in range(3, num+1):
    result = n1 + n2
    n1, n2 = n2, result
  return result
```

**재귀함수 사용**

```python
def fibonacci_recursive(num):
  if num < 2:
    return num
  return fibonacci_recursive(num-1) + fibonacci_recursive(num-2)
```


**재귀함수와 메모이제이션 사용**

```python
memo = {1:1, 2:1}
@call_counter
def fibonacci_recursive_memo(num):
  if num == 0:
    return 0
  if num not in memo:
    memo[num] = fibonacci_recursive_memo(num-1) + fibonacci_recursive_memo(num-2)
  return memo[num]
```


**파이썬 튜플 사용**

```python
def fibonacci_python(num):
  a, b = 1, 0
  for i in range(num):
    a, b = b, a + b
  return b
```

**성능 결과**

파이썬의 튜플을 이용해서 반복문으로 구현한 함수가 가장 빠르다.
재귀함수는 가장 느리기도 하고, 40을 입력했을 때 함수 호출이 331160281번으로 늘어난다. 숫자가 너무 커서 이게 맞는 건지 확인해 봐야 한다.
재귀함수에서 한번 계산한 값을 기억해서 다시 계산하는 방법을 메모이제이션이라고 한다. 메모이제이션을 적용하면 77번 호출로 줄어든다. 그래도 반복문보다 느리다.

```
Enter number for fibonacci> 40

function call count(calc): 1
elaspsed time(calc): 1.811981201171875e-05
result: 102334155

function call count(recursive): 331160281
elaspsed time(recursive): 82.3062391281128
result: 102334155

function call count(memo): 77
elaspsed time(memo): 4.673004150390625e-05
result: 102334155

function call count(python): 1
elaspsed time(python): 8.106231689453125e-06
result: 102334155
```
