---
layout : post
title : 국비지원 알게 된 것-1
subtitle :  국비지원 알게 된 것-1
category : machine learning
tags : 국비지원
date : 2019-03-12 15:00:00
---


(1). 쥬피터 경로 바꾸는 방법

a. jupyter notebook의 속성에 들어가 시스템의 경로 제일 뒤에 %로 이루어진 경로를 지운다.
b. jupyter notebook --generate-config을 cmd에 쳐서 폴더를 만든다.
c. config 파일의 261줄의 c.NotebookApp.notebook_dir = '' 에서 따음표 사이에 내가 넣고 싶은 경로를 저장한다.
   만약 주석이 있다면 주석을 지운다.
d. 쥬피터 노트북을 다시 실행해서 확인한다.

주의 : 쥬피터 노트북의 원래 경로는 사용자에 있음.

(2). 환경변수의 의미

a. 환경변수는 어느 지점이라도 내가 지정한 경로에 있는 파일들은 다 열 수 있게 해주는 변수
b. anaconda3와 Scropts까지는 지정해 두는게 좋음.
c. jupyter notebook이 다른데 있어서 경로를 다시 설정해야 됐는데 쉽게 anaconda를 깔 때 환경변수를 설정해주면 좋음.

(3). 인터프리터와 컴파일러의 차이

                 컴파일러            인터프리터

번역 단위         전체 				          한 줄씩

실행 속도         빠름                  느림

번역 속도          느림                 빠름

목적 프로그램   생성하지 않음          생성함

메모리 할당    목적 프로그램 생성시 사용    사용 안함
