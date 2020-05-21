---
layout : post
title :  HTML과 JavaScript의 만남 1(script 태그)
subtitle :  HTML과 JavaScript의 만남 1(script 태그)
category : 프로그래밍 언어 공부
tags : javascript
date : 2020-04-08 16:06:00
---

이 글은 [생활코딩 WEB2-javascript](https://opentutorials.org/course/3085)을 보고 정리한 글입니다


# 1. HTML과 JavaScript의 만남 1(Script 태그)

- 자바스크립트(JS)는 html 안에 들어가는 언어이다.  
- JS는 script태그 안에서 동작한다.

```html
<script>
  document.write('hello world');
</script>
```

- 위의 코드를 입력하면 그냥 html과 똑같이 hello world가 나온다. 다른 점은 자바스크립트 언어는 코드를 쓸 수 있다는 점이다. for문, if문을 사용해서 웹에 나타나는 문장들이 조건에 의해서 달라질 수 있다.

# 2. HTML과 JavaScript의 만남 2(이벤트)

- 이벤트란 웹에서 일어나는 변화, 사건이라고 생각하면 된다.  
- 값이 변하거나 버튼을 누르거나 하는 것이 다 이벤트이다.
- 이벤트는 전부 동적, 이 말은 자바스크립트를 사용한다는 뜻이다.    

이벤트를 알아보기 전 알아야 할 input태그를 밑의 코드와 설명을 통해서 알아보자.  


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>javatutorial</title>
  </head>
  <body>
    <input type="button" value="hi">
  </body>
</html>
```

## input 태그  
버튼, 텍스트 등 여러 항목을 넣을 수 있는 태그

#### type 속성
항목의 종류를 결정

- text : 텍스트를 넣어라  
- password : 비밀번호로 지정되어 어떤 것을 넣든 \*\*표시되라.  
- chekbox : 체크박스를 넣어라  
- radio : 라디오 버튼을 넣어라  
- image : 이미지를 넣어라 type속성 뒤에 무조건 src속성이 와서 경로 및 주소를 넣음.  
- submit : 전송버튼을 넣어라  
- button : 버튼을 넣어라  

#### value 속성  
항목 안에 넣을 텍스트를 결정  



## 이벤트 속성

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>javatutorial</title>
  </head>
  <body>
    <input type="button" value="hi" onclick = 'alert("hi")'>
    <input type="text" onchange="alert('how are you')">
    <input type="text" onkeydown="alert('Im fine thank you')">
  </body>
</html>
```

- onclick : 버튼을 누르면 값에 있는 자바스크립트 언어를 실행시켜라

- onchange : 텍스트 박스 안에 값이 바뀌면 자바스크립트 언어를 실행시켜라.

- onkeydown : 글자를 입력한 순간 자바스크립트 언어를 실행시켜라


# 3. HTML과 JavaScript의 만남3(콘솔)

- 크롬에서 개발자 도구에 들어가면 콘솔에서 자바스크립트를 이용할 수 있다.  
- 코딩은 웹사이트를 만드는 것 뿐만 아니라 내가 가지고 있는 문제들을 가볍게 해결할 도구로써도 사용할 수 있다.


#4. 데이터 타입 - 문자열과 숫자  



- jekyll을 이해하기 위해서 이 강의를 들었으나 {%}가 자바스크립트 언어가 아니라느 ㄴ것을 깨닫고 잠시 작성을 멈춤.   
- 다시 자바스크립트 언어가 필요할 때가 되면 작성할 것.
