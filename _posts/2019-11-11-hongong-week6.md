---
layout: post
title: '혼자 공부하는 파이썬 - 6주차 미션'
date: 2019-11-11 20:00
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
![결과화면](assets/images/beautiful_flask.jpg))

## 선택미션
혼공 용어 노트에 나만의 언어로 객체, 클래스, 인스턴스, 생성자, 메소드 보충 설명쓰고 인증샷
