---
layout: post
title: '혼자 공부하는 파이썬 - 1주차 미션'
date: 2019-10-09 21:00
categories: [language, python]
# os, windows, linux, 
# service, github
# language, python, c
# etc, blog
---

# 1 주차
## 기본 미션
63쪽 3~5번 실행결과 쓰고 인증샷

#### 63쪽 3번
다음 프로그램의 실행결과를 예측해 보세요.
```python
print("# 연습문제")
print("\\\\\\\\")
print("-" * 8)
```

실행결과 예측
* "" 사이의 문자열을 모두 출력한다.
* '\'(역슬래시)는 이스케이프 문자라서 두개를 하나씩 출력한다. 8개이므로 4개 출력한다.
* 문자열에 곱하기 연산 가능하다. '-'를 8번 반복해서 출력한다.

실행결과
```bash
PS C:\작업\hongong-python> python 02-1-3.py
# 연습문제
\\\\
--------
```

#### 63쪽 4번
다음 프로그램의 실행결과를 예측해 보세요. 그런데, 이 예제를 실행하면 오류가 발생합니다. 몇 행에서 어떤 오류가 발생할까요? 그리고 그 이유는 무엇인지 말해 보세요.
```python
print("안녕하세요"[1])
print("안녕하세요"[2])
print("안녕하세요"[3])
print("안녕하세요"[4])
print("안녕하세요"[5])
```

실행결과 예측
* 문자열 뒤에 인덱스를 이용하여 문자를 출력한다.
* 인덱스는 0부터 시작한다. 첫문자는 [0]이다.
* 문자열에 없는 인덱스를 지정하면 오류(IndexError)가 발생한다.

실행결과
```bash
PS C:\작업\hongong-python> python 02-1-4.py
녕
하
세
요
Traceback (most recent call last):
  File "02-1-4.py", line 6, in <module>
    print("안녕하세요"[5])
IndexError: string index out of range
```

#### 63쪽 5번
다음 프로그램의 실행결과를 예측해 보세요.
```python
print("안녕하세요"[1:3])
print("안녕하세요"[2:4])
print("안녕하세요"[1:])
print("안녕하세요"[:3])
```

실행결과 예측
* 슬라이싱을 이용하여 문자열의 일부로 문자열을 생성한다.
* 슬라이싱은 인덱스처럼 0부터 시작하고 끝은 포함하지 않는다.
* 인덱스의 처음과 끝은 모두 생략할 수 있다.

실행결과
```bash
PS C:\작업\hongong-python> python 02-1-5.py
녕하
하세
녕하세요
안녕하
```

## 선택 미션
모르는 용어(3~5개) 찾아 혼공 용어 노트에 정리하고 인증샷
한글로 제공되는 [파이썬 3.7 용어집(https://docs.python.org/ko/3/glossary.html#glossary)도 참고해 보세요.

#### 인터프리터
* 프로그래밍 언어의 소스 코드를 바로 실행하는 컴퓨터 프로그램 또는 환경
* 다음 3가지 기능 중에 한가지 이상의 기능을 갖는다
  - 소스 코드를 직접 실행한다.
  - 소스 코드를 효율적인 다른 중간 코드로 변환하고, 변환한 것을 바로 실행한다
  - 인터프리터 시스템의 일부인 컴파일러가 만든, 미리 컴파일된[1] 저장 코드의 실행을 호출한다.
* 원시 코드를 기계어로 번역하는 컴파일러와 대비된다 

#### 통합 개발 환경
* Integrated Development Environment - IDE
* 텍스트 에디터와 코드 실행기 두가지 기능 포함

#### 인터렉티브 셀
* 대화형 셀
* 파이썬의 경우 프롬프트 >>> 에 코드를 입력하면 실행하는 인터렉티브 셀을 제공한다.

#### 구문오류
* Syntax Error
* 작성한 코드에 문제가 있어서 실행되지 않음을 의미

#### [이스케이프 문자](https://ko.wikipedia.org/wiki/이스케이프_문자)
* 문자열 내부에서 특수한 기능을 수행하는 문자열
* 시퀀스를 따르는 문자들로서 다음 문자가 특수 문자임을 알리는 백슬래시(\)를 사용한다. 
* 일부 제어 시퀀스인 이스케이프 문자들은 미리 예약되어있다. 

## 혼자 공부하는 프로그래밍 - 파이썬
혼자 공부하는 프로그래밍 [파이썬-소개](https://godsman-yang.github.io/hongong-python)와 미션을 정리했습니다.
* [1주차 미션](https://godsman-yang.github.io/hongong-week1) 
* [2주차 미션](https://godsman-yang.github.io/hongong-week2) 
* [3주차 미션](https://godsman-yang.github.io/hongong-week3) 
* [4주차 미션](https://godsman-yang.github.io/hongong-week4) 
* [5주차 미션](https://godsman-yang.github.io/hongong-week5) 
* [6주차 미션](https://godsman-yang.github.io/hongong-week6) 

## 미션 외 자료 정리
[혼공 노트](https://godsman-yang.github.io/hongong-note)
