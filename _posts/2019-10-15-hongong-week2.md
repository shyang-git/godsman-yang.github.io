---
layout: post
title: '혼자 공부하는 파이썬 - 2주차 미션'
date: 2019-10-14 09:00
categories: coding
---

# 2 주차
## 기본 미션
137쪽 3번 문제 풀고 본인이 태어난 해와 띠를 출력하는 결괏값 화면 인증샷

#### 137쪽 3번
사용자에게 태어난 연도를 입력받아 띠를 출력하는 프로그램을 작성해 주세요. 작성 시 입력받은 연도를 12로 나눈 나머지를 사용합니다. 나머지가 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11일때 각각 원숭이, 닭, 개, 돼지, 쥐, 소, 범, 토끼, 용, 뱀, 말, 양띠입니다.
[미션 소스](https://github.com/godsman-yang/hongong-python/blob/master/03-2-3.py)와 [리팩토링 소스](https://github.com/godsman-yang/hongong-python/blob/master/03-2-3-rf.py)를 참고하세요.

```python
str_input = input("태어난 해를 입력해 주세요> ")
birth_year = int(str_input)

if(birth_year%12) == 0:
    print("원숭이 띠입니다.")
elif(birth_year%12) == 1:
    print("닭 띠입니다.")
elif(birth_year%12) == 2:
    print("개 띠입니다.")
elif(birth_year%12) == 3:
    print("돼지 띠입니다.")
elif(birth_year%12) == 4:
    print("쥐 띠입니다.")
elif(birth_year%12) == 5:
    print("소 띠입니다.")
elif(birth_year%12) == 6:
    print("범 띠입니다.")
elif(birth_year%12) == 7:
    print("토끼 띠입니다.")
elif(birth_year%12) == 8:
    print("용 띠입니다.")
elif(birth_year%12) == 9:
    print("뱀 띠입니다.")
elif(birth_year%12) == 10:
    print("말 띠입니다.")
elif(birth_year%12) == 11:
    print("양 띠입니다.")
```

코드분석
책의 예제는 elif를 설명하기에 충분하다.
실제 제품이나 서비스를 개발할 경우를 생각해서 몇가지 개선사항(리팩토링)을 생각해 본다.
* birth_year에 따라 비교문의 개수가 다르다.
  - 예를들어 원숭이 띠는 1번 비교로 알 수 있고, 양 띠는 12번 비교를 해야 한다.
  - 마지막 양 띠의 elif를 else로 변경한다면 11번 비교를 한다.
* birth_year를 매번 연산한다.
  - 처음에 ```birth_year_mod12 = birth_year%12```를 구해 놓으면 1번 연산
  - 언어의 컴파일러에 따라서 저런 형태는 한번만 연산하도록 최적화하는 경우도 있다.
* 코드 중복
  - 출력되는 문자열은 "{연산한 띠} 띠입니다."
  - 띠는 사전에 정의되어 있음

리팩토링
* 띠는 튜플로 저장
* 나머지 연산의 결과를 튜플의 인덱스로 사용
```python
chinese_zodiac_sign = ('원숭이', '닭', '개', '돼지', '쥐', '소', '범', '토끼', '용', '뱀', '말', '양')

str_input = input("태어난 해를 입력해 주세요> ")
birth_year_mod = (int(str_input))%12

print(chinese_zodiac_sign[birth_year_mod], "띠입니다.")
```

## 선택 미션
else 구문과 elif 구문 정리한 내용 포스팅하기

#### if-else 문
* 제어문, 조건문
  - 조건을 비교하여 조건과 맞으면(True 이면) if 코드블록을 실행한다
  - 조건과 맞지 않으면()False 이면) else 코드블록을 실행한다.

#### elif 필요
* 조건 중첩되어 여러 단계가 필요한 경우
  - else 문 안에 if가 필요한 경우
* 여러가지 조건이 있는 경우
  - if 문이 여러개 필요한 경우
  - 조건이 중복되는 경우는 if-else 를 여러 번 사용한다.
  - 조건이 중복되지 않는 경우는 이미 비교한 조건은 비교하지 않을 필요가 있다.
* 파이썬의 경우 else 문에 조건을 넣을 수 있는 elif를 제공한다.
  - 다른 언어도 표기법은 다르지만 else-if 문을 제공한다.

#### 조건문 형태
* if-else if-else/if-elif-else
* switch-case - 파이썬에는 없고, C/C++, Java에서 지원
* 참고 [위키백과 조건문](https://ko.wikipedia.org/wiki/%EC%A1%B0%EA%B1%B4%EB%AC%B8)