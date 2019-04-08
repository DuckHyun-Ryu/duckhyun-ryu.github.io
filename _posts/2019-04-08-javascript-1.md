---
layout : post
title : javascript-1
subtitle : javascript-1
category : 프로그래밍 언어 공부
tags : javascript
date : 2019-04-08 18:00:00
---
html안에서 코드를 작성하고 싶을 때 사용하는 언어

(1) 스크립트 언어 : perl, vbscript,...
(2) 객체기반언어
(3) 사용방법
a. inline style
-태그안에서 작성
b. internal style
-페이지내에서 작성
c. external style
-별도의 파일로 작성(.js)


### inline 예시

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body onload = "i = '나는 변수다' ;document.write(i+'<br>')">
이런식으로 태그안에서 javascript 언어를 직접 넣을 때 사용
</body>
</html>
```



### internal 예시
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<script>   // 이 부분이 javascript 부분
    i = 10;
    document.write(i+"<br>")

    i = '이번엔 문자열';
    document.write(i+'<br>')

    var a = 20, b = '20', c;
    c = a == b;
    document.write(c + '<br>');


</script>

</head>
<body>
  <h2>1부터 10까지 카운터</h2>
  <script>
    for( i = 1; i<=10; i++){
      document.write(i + "<br>");
    }
   </script>


</body>
</html>
```
### external 예시

```html


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src = "../js/external.js"></script>   // 이렇게 js폴더부분을 경로로 지정한다.
</head>
</head>
<body>

</body>
</html>
```
