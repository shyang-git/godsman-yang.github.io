---
layout: post
title: "혼자 공부하는 머신러닝 + 딥러닝 - 6주차 미션"
date: 2021-03-07 23:50
categories: [language, python, machine learning, deep learning]
# os, windows, linux,
# service, github
# language, python, c
# etc, machie learning, deep learning, blog
author: godsman-yang
---

# 6 주차

## 기본 미션

7-1절 문제 풀고 인증샷

#### 7-1절 문제 풀고 인증샷

1. 어떤 인공 신경망의 입력 특성이 100개이고 밀집층에 있는 뉴런 개수가 10개일 때 필요한 모델 파라미터의 개수는 몇 개인가요?

- 1,010개
  - 100 x 10 + 10

2. 케라스의 Dense 클래스를 사용해 신경망의 출력층을 만들려고 합니다. 이 신경망이 이진 분류 모델이라면 activation 매개변수에 어떤 활성화 함수를 지정해야 하나요?

- sigmoid
  - dense = keras.layers.Dense(10, activation='sigmoid', input_sape=(784,))

3. 케라스 모델에서 손실 함수와 측정 지표 등을 지정하는 메서드는 무엇인가요?

- compile()
  - 모델 객체를 만든 후 훈련하기 전에 사용할 손실 함수와 측정 지표 등을 지정하는 메서드
  - model.compile(loss='sparse_categorical_crossentropy', metrics='accuracy')

4. 정수 레이블을 타깃으로 가지는 다중 분류 문제일 때 케라스 모델의 compile() 메서드에 지정할 손실 함수로 적절한 것은 무엇인가요?

- sparse_categorical_crossentropy

  - 클래스 레이블이 정수: sparse_categorical_crossentropy

- 손실 함수 참고
  - 이진 분류:loss = 'binary_crossentropy'
  - 다중 분류:loss = 'categorical_crossentropy'
  - 클래스 레이블이 정수:loss = 'sparse_categorical_crossentropy'
  - 회귀 모델:loss = 'mean_square_error'

## 선택 미션

7-2절 문제 풀고 인증샷

#### 7-2절 문제 풀고 인증샷

1. 다음 중 모델의 add() 메서드 사용법이 올바른 것은 어떤 것인가요?

- model.add(keras.layers.Dense(10, activation='relu'))
  - 케라스 모델에 층을 추가하는 메서드

2. 크기가 300 x 300인 입력을 케라스 층으로 펼치려고 합니다. 다음 중 어떤 층을 사용해야 하나요?

- Flatten

  - 1차원으로 펼치기 위해 reshape() 메서드를 사용
  - 케라에서는 Flatten 층을 제공

3. 다음 중에서 이미지 분류를 위한 심층 신경망에 널리 사용되는 케라스의 활성화 함수는 무엇인가요?

- relu

  - 초창기 인경 신경망의 은닉층에 많이 사용된 활성화 함수는 시그모이드 함수
  - 시그모이드 함수는 올바른 출력을 만드는데 신속하게 대응하기 어려움, 특히 많은 심층 신경망일수록
  - 시그모이드함수를 개선하기 위해 렐루 함수가 제안됨. 심층 신경망에서 뛰어남

4. 다음 중 적응적 학습률을 사용하지 않는 옵티마이저는 무엇인가요?

- SGD

  - 모델이 최적점에 가까이 갈수록 학습률을 낮출 수 있고 안정적으로 최적점에 수렴할 가능성이 높음
  - 이런 학습률을 적응적 학습률이라고 함

- 대표적인 옵티마이저
  - Adagrad
  - RMSprop
  - Adam

## 혼자 공부하는 프로그래밍 - 머신러닝 + 딥러닝

혼자 공부하는 프로그래밍 [머신러닝+딥러닝-소개](https://godsman-yang.github.io/hongong-ml)와 미션을 정리했습니다.

- [1주차 미션](https://godsman-yang.github.io/hongong-ml-week1)
- [2주차 미션](https://godsman-yang.github.io/hongong-ml-week2)
- [3주차 미션](https://godsman-yang.github.io/hongong-ml-week3)
- [4주차 미션](https://godsman-yang.github.io/hongong-ml-week4)
- [5주차 미션](https://godsman-yang.github.io/hongong-ml-week5)
- [6주차 미션](https://godsman-yang.github.io/hongong-ml-week6)
