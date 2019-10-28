---
layout: post
title: '혼자 공부하는 파이썬 - 3주차 미션'
date: 2019-10-21 09:00
categories: [language, python]
# os, windows, linux, 
# service, github
# language, python, c
# etc, blog, jekyll
---

# 3 주차
기본 미션: 리스트, 딕셔너리, 범위 자료형에 대해 이해한 내용을 바탕으로 포스팅하기
선택 미션: 157쪽의 1번 문제의 답 쓰고 인증샷

## 기본 미션
리스트, 딕셔너리, 범위 자료형에 대해 이해한 내용을 바탕으로 포스팅하기
혼자 공부하는 파이썬 동영상에서 [18강](https://www.notion.so/shyang4x/3-c08960528a6e488894306b4228ad3e01#f59123ef51fc48e69be562db4a79b7b2)부터 4장을 강의합니다. 
저장의 동영상 강의를 기본으로 정리해 보았습니다. 가능하면 들으면서 실시간 정리합니다.

## 리스트
리스트는 목록이고, 목록은 순서 없는 목록과 순서 있는 목록으로 나눌 수 있다.
프로그램에서 리스트는 순서가 있는 목록이라고 생각하면 된다.
파이썬은 목록의 순서가 0부터 시작한다.
파이썬의 리스트는 여러 자료형을 혼합해서 입력할 수 있다.

```python
a = ['수박', '바나나', '키위', 1, 2, True]
```

리스트 선택 연산자
- 인덱스 a[0] - 0부터 시작, 음수도 가능 a[-1]
- 슬라이싱 a[3:] - [1, 2, True]

당황할 수 있는 기능
- 중첩 리스트 - 리스트 안에 리스트 포함 가능

리스트에서 자주 발생하는 오류
- 리스트의 범위 오류 - 슬라이싱에서는 발생하지 않음

리스트 연산자
- 리스트 연결 +
- 리스트 반복 *
- 포함 in, 포함하지 않음 not in

리스트 함수
- append - 마지막에 추가
- insert - 특정 위치에 추가
- extend - 리스트에 여러가지 요소를 추가할 때

파괴적인 함수/비파괴적인 함수
- 자기 자신이 파괴하지 않는 함수 - 비파괴적인 함수 - 함수에서 나오는 결과를 사용함
- 리스트의 함수는 대부분 파괴적입니다. - 외워야 합니다.
- 일반적으로 대부분의 함수는 비파괴적이다.
- 리스트처럼 사이즈가 변할 수 있는 것을 비파괴적으로 구현한다면 메모리가 많이 사용될 수 있으므로 파괴적일 것으로 생각한다.
- a.append(4) 는 파괴적인 방법, a + [4] 는 비파괴적인 방법

요소 제거하는 방법
- 인덱스로 제거
    - del 연산자 - del a[1], del a[0:3]
    - pop() 함수 - a.pop(1), 제거되는 값이 리턴됨, 인덱스를 지정하지 않으면 마지막 값이 제거됨
- 값으로 제거
    - remove() 함수 - a.remove(100), 100값이 제거됨. 내부에 값이 여러 개이면 하나만 제거됨.
        - 모든 값을 제거하려면, 반복문, 필터, 중첩반복문

## 딕셔너리
딕셔너리는 리스트와 비슷하다.
딕셔너리는 중괄호 {}를 이용한다. 키와 값을 입력한다.
딕셔너리["키A"] 형태로 값을 구할 수 있음
딕셔너리의 값을 변경이 가능함.
딕셔너리에 값을 추가하고 삭제하는 방법
- 딕셔너리["키"] = "값"
- del 딕셔너리["키"]

강의 예제 참고

```pyton
    # 딕셔너리 선언
    딕셔너리 = {
        "문자열": "값",
        273: [1, 2, 3, 4],
        True: False
    }
    
    # 반복문
    for key in 딕셔너리:
        print("{} : {}".format(key, 딕셔너리[key]))
    # 요소 추가
    딕셔너리["키"] = "값"
    print()
    for key in 딕셔너리:
        print("{} : {}".format(key, 딕셔너리[key]))
    print()
    del 딕셔너리["키"]
    print()
    for key in 딕셔너리:
        print("{} : {}".format(key, 딕셔너리[key]))
```

딕셔너리에서 안전에게 꺼내기
- 없는 키를 꺼내려고 하면 오류가 발생함 - KeyError
- 딕셔너리 내부에 키가 있는지 확인하고 가져옴 ``` key in dictionary ```
- dictionary.get("키") - 없는 요수에 접근하면 'None'을 리턴함
    - 에러를 리턴하지 않지만 비교구문은 필요하다.

## 범위 자료형
범위는 range 이고 자료형이다.
range(시작, 끝, 단계) ⇒ range(0, 10, 1)
- 끝은 범위에 포함되지 않음
- 단계가 생략되면 1로 인식
- 시작이 생략되면 0부터 시작

일반적으로 range는 반복문에서 회수로 사용함
리스트를 순서(인덱스)와 함께 출력할 때 enumerate와 range 사용함
```pyton
    # 인덱스 출력의 세가지 방법
    array = [273, 52, 103, 32, 57]
    
    # 첫번째 i를 인덱스로 사용 - C언어 형태
    i = 0
    for element in array:
        print("{} : {}".format(i, element)) 
        i += 1
    
    # 두번째 enumerate 함수 사용 - 인덱스와 값을 리턴
    for i, element in enumerate(array):
        print("{} : {}".format(i, element)) 
    
    # 세번째 range 함수 사용 - 인덱스를 이용
    for i in range(len(array)):
        print("{} : {}".format(i, array[i]))
```

역반복문
- for i in range(10, 0-1, -1):
- for i in reversed(range(0, 10)):

# 선택미션
157쪽의 1번 문제의 답 쓰고 인증샷

list_a = [0, 1, 2, 3, 4, 5, 6, 7]입니다. 다음 표의 함수들을 실행했을 때 list_a의 결과가 어떻게 나오는지 적어 보세요.
```
    # extend - 리스트에 요소 추가
    list_a = [0, 1, 2, 3, 4, 5, 6, 7]
    list_a.extend(list_a)
    print("list_a.extend(list_a)", list_a)
    
    # append - 리스트에 마지막에 추가
    list_a = [0, 1, 2, 3, 4, 5, 6, 7]
    list_a.append(10)
    print("list_a.append(10)", list_a)
    
    # insert - 리스트 특정한 위치(인덱스)에 값 추가
    list_a = [0, 1, 2, 3, 4, 5, 6, 7]
    list_a.insert(3, 0)
    print("list_a.insert(3, 0)", list_a)
    
    # remove - 리스트에서 값 삭제, 하나만 삭제됨
    list_a = [0, 1, 2, 3, 4, 5, 6, 7]
    list_a.remove(3)
    print("list_a.remove(3)", list_a)
    
    # pop - 리스트에서 특정한 위치(인덱스)의 값 삭제
    list_a = [0, 1, 2, 3, 4, 5, 6, 7]
    list_a.pop(3)
    print("list_a.pop(3)", list_a)
    
    # clear - 리스트 전체 삭제
    list_a = [0, 1, 2, 3, 4, 5, 6, 7]
    list_a.clear()
    print("list_a.clear()", list_a)
```

[혼자 공부하는 파이썬 18강 - 리스트 기본](https://youtu.be/dYykqm41jfY)