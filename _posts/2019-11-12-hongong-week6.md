---
layout: post
title: '혼자 공부하는 파이썬 - 6주차 미션'
date: 2019-11-12 08:00
categories: [language, python]
# os, windows, linux, 
# service, github
# language, python, c
# etc, blog, jekyll
---

# 6 주차
342쪽의 [직접 해보는 손코딩:BeautifulSoup 스크레이핑 실행하기] 예제 실행 후 결과 화면 인증샷

혼공 용어 노트에 나만의 언어로 객체, 클래스, 인스턴스, 생성자, 메소드 보충 설명쓰고 인증샷

## 기본 미션
342쪽의 [직접 해보는 손코딩:BeautifulSoup 스크레이핑 실행하기] 예제 실행 후 결과 화면 인증샷

beautiful_flask.py
```python
# 모듈을 읽어 들입니다.
from flask import Flask
from urllib import request
from bs4 import BeautifulSoup

# 웹 서버를 생성합니다.
app = Flask(__name__)
@app.route("/")

def hello():
  # urlopen() 함수로 기상청의 전국 날씨를 읽습니다.
  target = request.urlopen("http://www.kma.go.kr/weather/forecast/mid-term-rss3.jsp?stdId=108")

  # BeautifulSoup를 사용해 웹 페이지를 분석합니다.
  soup = BeautifulSoup(target, "html.parser")

  # location 태그를 찾습니다.
  output = ""
  for location in soup.select("location"):
    # 내부의 city, wf, tmn, tmx 태그를 찾아 출력합니다.
    output += "<h3>{}</h3>".format(location.select_one("city").string)
    output += "날씨: {}</br>".format(location.select_one("wf").string)
    output += "최저/최고 기온: {}/{}".format(location.select_one("tmn").string, location.select_one("tmx").string)
    output += "<hr/>"
  return output
```

결과 화면
![결과화면](assets/images/beautiful_flask.jpg)

## 선택미션
혼공 용어 노트에 나만의 언어로 객체, 클래스, 인스턴스, 생성자, 메소드 보충 설명쓰고 인증샷

#### 객체
혼공 용어 노트 설명
* 여러 가지 속성을 가질 수 있는 대상

추가 설명
* 사물을 프로그래밍에서 사용할 수 있도록 추상화한 개념
* 사람이나 동물 또는 책과 같은 사물을 객체라고 할 수 있다.

#### 클래스
혼공 용어 노트 설명
* 객체에 포함할 변수와 함수를 미리 정의한 것
* 객체의 설계도에 해당

추가 설명
* 객체를 프로그래밍 언어로 정의한 것
* 객체를 클래스로 표현할 때 객체 고유의 성질은 (멤버)변수로, 객체가 하는 일은 (멤버)함수로 구현
* 고양이라면, 품종이나 나이는 (멤버)변수로 나타내고, 뛴다, 먹는다는 (멤버)함수로 구현한다.  


#### 인스턴스
혼공 용어 노트 설명
* 클래스 기반으로 만들어진 객체

추가 설명
* 클래스가 객체를 추상화한 개념이라면 인스턴스는 클래스의 실체
* 고양이가 클래스라면, 우리집에 있는 고양이, 야옹이는 인스턴스이다. 

#### 생성자
혼공 용어 노트 설명
* 클래스 이름과 같은 함수
* 클래스 내부에 __init__ 이라는 함수를 만들면 생성할 때 처리를 작성할 수 있다.

추가 설명
* 클래스를 인스턴스로 실체화될 때 수행하는 함수, 인스턴스가 생성될 때 실행된다고 해서 생성자라고 한다.

#### 메소드
혼공 용어 노트 설명
* 클래스가 가지고 있는 함수

추가 설명
* 클래스에서 사용할 수 있는 함수. 언어에 따라 멤버 함수나 인스턴스 함수라고 하기도 한다.
* 클래스 내부의 (멤버)변수에 접근이 가능한 함수이다

## 혼자 공부하는 프로그래밍 - 파이썬
* [1주차 미션](https://godsman-yang.github.io/hongong-week1) 
* [2주차 미션](https://godsman-yang.github.io/hongong-week2) 
* [3주차 미션](https://godsman-yang.github.io/hongong-week3) 
* [4주차 미션](https://godsman-yang.github.io/hongong-week4) 
* [5주차 미션](https://godsman-yang.github.io/hongong-week5) 
* [6주차 미션](https://godsman-yang.github.io/hongong-week6) 