---
layout: post
title: "혼자 공부하는 머신러닝 + 딥러닝 - 5주차 미션"
date: 2021-02-28 23:20
categories: [language, python, machine learning, deep learning]
# os, windows, linux,
# service, github
# language, python, c
# etc, machie learning, deep learning, blog
author: godsman-yang
---

# 5 주차

## 기본 미션

k-평균 알고리즘 작동 방식 설명하기

#### k-평균 알고리즘 작동 방식 설명하기

k-평균(k-means) 군집 알고리즘이 평균값을 자동으로 찾아줍니다.

k-평균 알고리즘 소개

1. 무작위로 k개의 클러스터 중심을 정합니다.
2. 각 샘플에서 가장 가까운 클러스터 중심을 찾아 해당 클러스터의 샘플로 지정합니다.
3. 클러스터에 속한 샘플의 평균값으로 클러스터 중심을 변경합니다.
4. 클러스터 중심에 변화가 없을 때까지 2번으로 돌아가 반복합니다.

그림으로 나타내면 다음과 같습니다.
![k-평균 알고리즘 작동 방식](./assets/images/hongong-ml-week5-1.jpg)

- k-평균 알고리즘은 처음에는 랜덤하게 클러스터 중심을 선택하고 점차 가장 가까운 샘플의 중심으로 이동하는 비교적 간단한 알고리즘입니다.

## 선택 미션

6-3절 문제 풀고 인증샷

#### 6-3절 문제 풀고 인증샷

1. 특성이 20개인 대량의 데이터셋이 있습니다. 이 데이터셋에서 찾을 수 있는 주성분 개수는 몇 개일까요?

- 20개
  - 주성분 분석은 차원 축소 알고리즘의 하나로 데이터에서 가장 분산이 큰 방향을 찾는 방법입니다.
  - 이런 방향을 주성분이라고 부릅니다.
  - 원본 데이터를 주성분에 투영하여 새로운 특성을 만들 수 있습니다.
  - 일반적으로 주성분은 원본 데이터에 있는 특성 개수보다 작습니다.

2. 샘플 개수가 1,000개이고 특성 개수는 100개인 데이터셋이 있습니다. 즉 이 데이터셋의 크기는 (1000, 100)입니다. 이 데이터를 사이킷런의 PCA 클래스를 사용해 10개 주성분을 찾아 변환했습니다. 변환된 데이터셋의 크기는 얼마일까요?

- (1000, 10)
  - 데이터셋에서 주성분 개수를 변환하면 샘플의 개수는 그대로 이고, 주성분의 개수는 변경됩니다.
  - 샘플의 개수는 1,000개이고
  - 주성분의 개수를 10개로 변환했으므로
  - 데이터셋의 크기는 (1000, 10)이 됩니다.

3. 2번 문제에서 설명된 분산이 가장 큰 주성분은 몇 번째인가요?

- 첫 번째 주성분

  - 주성분이 원본 데이터와 분산을 얼마나 잘 잘나타내는지 기록한 값을 설명된 분산(explained variance)이라고 합니다.
  - PCA 클래스의 explained_variance_ratio에 각 주성분의 설명된 분산 비율이 기록되어 있습니다.
  - 첫 번째 주성분의 설명된 분산이 가장 큽니다.

## 혼자 공부하는 프로그래밍 - 머신러닝 + 딥러닝

혼자 공부하는 프로그래밍 [머신러닝+딥러닝-소개](https://godsman-yang.github.io/hongong-ml)와 미션을 정리했습니다.

- [1주차 미션](https://godsman-yang.github.io/hongong-ml-week1)
- [2주차 미션](https://godsman-yang.github.io/hongong-ml-week2)
- [3주차 미션](https://godsman-yang.github.io/hongong-ml-week3)
- [4주차 미션](https://godsman-yang.github.io/hongong-ml-week4)
- [5주차 미션](https://godsman-yang.github.io/hongong-ml-week5)
