---
layout: post
title: '혼자 공부하는 파이썬 - 5주차 미션'
date: 2019-10-30 20:00
categories: [language, python]
# os, windows, linux, 
# service, github
# language, python, c
# etc, blog, jekyll
---

# 5 주차
구문 오류와 예외의 차이 설명하기(291쪽 1번 문제)

293쪽 3번 문제 풀고 인증샷

## 기본 미션
구문 오류와 예외의 차이 설명하기(291쪽 1번 문제)

### 관련 용어
오류는 크게 두가지로 나눌 수 있다.
- 구문 오류(Syntax Error)
- 예외(Exception)

#### 구문 오류(Syntax Error)
코드에 문제가 있어서 실행 자체가 되지 않는 문제
- 실행 전에 발생한다
- 문법적인 문제를 해결해서 해결할 수 있다
- SyntaxError
- 실행 전에 오류가 있는 걸 알 수 있으므로 쉽게 해결할 수 있다.

#### 예외(Exception)
코드 자체 문법적인 오류는 없지만 실행과 관련된 문제
- 실행 후에 발생한다
- 예외처리를 통해서 해결할 수 있다.
- 예외는 일단 실행은 된다. 실행 시 예외 발생 위치에서 프로그램이 죽는다.
- 예외를 처리하는 기본적인 방법
  - 조건문을 사용하여 예외를 발생하지 않는 경우에만 프로그램이 동작하도록 코딩한다
  - 모든 예외를 미리 예측하는 것이 어려우므로 예외처리 전용 구문을 활용한다

#### 예외처리 전용 구문 try-except
모든 예외를 미리 예측하는 것이 어렵다
메모리 부족과 같이 예외가 발생하는 상황을 알아내기 어렵다
- else 구문은 거의 사용하지 않는다
- finally 구문
  - 함수 내부에서 return 키워드를 사용하거나
  - 반복문 내부에서 break 키워드를 사용할 때 의미가 있음

#### 예외 객체
```python
  raise Exception("안녕하세요")
```

#### 참고용 소스
```python
try:
  # 예외가 발생할 수 있는 가능성이 있는 코드
  number = int(input("> 정수를 입력해 주세요: "))
  print("입력 값은 {}입니다.".format(number))
except ValueError as exception:
  print("값에 문제가 있습니다.")
except IndexError as exception:
  print("인덱스트에 문제가 있습니다.")
except Exception as exception:
  # 예외가 발생했을 때 실행할 코드
  print("알 수 없는 예외가 발생했습니다.")
finally:
  # 무조건적으로 실행하는 코드
  print("무조건적으로 실행됩니다.")
```

## 선택미션
293쪽 3번 문제 풀고 인증샷

숫자 + 문자열은 타입 예외 발생함
여는 괄호를 생략하면 구문 오류가 발생한다

```python
# 다음 중 구문 오류 발생이 예상되면 '구문 오류'에, 예외 발생이 예상되면 '예외'에 체크 표시를 한 후, 예상되는 에러명도 적어 보세요.

output = 10 + "개" #1 예외-TypeError
int("안녕하세요") #2 예외-ValueError
cursor.close) #3 구문 오류
[1, 2, 3, 4, 5][10] #4 예외-IndexError
```

```python
>>> output = 10 + "개"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

```python
>>> int("안녕하세요")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '안녕하세요'
```

```python
>>> cursor.close)
  File "<stdin>", line 1
    cursor.close)
                ^
SyntaxError: invalid syntax
```

```python
>>> [1, 2, 3, 4, 5][10] #4 예외-IndexError
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
