---
layout : post
title : 3.Six Types of Questions
subtitle : 3.Six Types of Questions Iteration
category : 강의 정리
tags : Managing Data Analysis
date : 2019-04-21 19:31:00
---


 ### 데이터 사이언스의 첫번째 시작 질문에는 6가지 타입이 있다.

(1) Descriptive
(2) Exploratory
(3) Inferential
(4) Predictive
(5) Casual
(6) Mechanistic


 (1) Descriptive Analysis

 데이터 셋의 기본 특징들을 묻는 질문
 데이터 이외에 것들에 대한 관심이 없다.

 (2) Exploratory Analysis(EDA)

데이터들의 흐름이나 변수의 관계를 알아보려는 질문
데이터 이외에 것들에 대한 관심은 없다.

주로 데이터 분석 프로젝트 초기에 가설을 수립하기 위해 수행되기도 한다.
목적업이 데이터를 탐험하다보면 끝이 없는데 아래 2가지를 염두해 두면 효율적으로 진행할 수 있다.

a. 분석의 목적을 염두해 두자

분석의 목적이 가설 수립인지, 특정 변수들간의 관계 파악인지, 트렌드 파악인지를 항상 머릿속에 가지고 있자.

b. reporoducty(재현 가능성)

우리의 분석이 다른 누군가가 하더라도 똑같은 결과가 나올 수 있또록 어떤 조건에서 그러한 그래프를 그렸는지를 확인하자.

 (3) Inferential Analysis

 샘플 - 모집단 간의 관계를 탐구하는 것이 목적이다.
 샘플에서 얻어낸 정보가 모집단에도 적용될 수 있는지를 검토하는 것이다.

 (4) Predictive Analysis

 machine learning, decision tree 등 다양한 통계적 기법을 사용하여 미래 혹은 발생하지 않은 어떤 사건에 대한 예측을 하는것이 목표이다.

 어떤 요인이 어떤 과정에 의해서 영향을 미치는데 관심이 있기 보다는 예측을 하는 것이 주요 관심사이기때문에 설명력은 약하다.

 예측 모델 속에 여러 의사 결정 옵션을 변수로 포함시킨 prescriptvie analysis도 주목을 받고 있다.

(5) Causal Analysis

독립 변수와 종속 변수간의 인과관계가 있는지 여부를 확인하는 것이 주 목적이다.
주로 실험을 통해 수집된 데이터를 대상으로 한다.
독립변수를 랜덤으로 할당한 후 그룹 간 실험 전/후의 종속변수의 변화를 관찰하여 실험데이터 수집이 이루어진다.
선형 regression이 가장 많이 사용되는 분석 방법이며, 변수가 여러 개일 경우 multi variable regression, 변수가 범주형일 경우 logistics regression을 사용한다.

(6) Mecanistic Analysis도

독립 변수가 어떤 매커니즘으로 종속 변수에 영향을 미치는지를 분석하는 것이다.
Causal analysis의 목적이 독립-종속 변수  간의 인과관계여부를 밝혀내는 것이라면 Mechanistic analysis의 목적은 이에 더해 어떠한 독립변수가 어떤 작용을 통해 독립 변수에 그러한 영향을 미치는 지를 이해하는 것이다.
