---
title: java html tag 정리
categories: [dev]
comments: true
---
java html tag 정리
=============

<>는 생략한다.

1.html

웹페이지의 시작과 끝을 지정하는 역할
  
html로 시작해서 /html로 끝난다.
  
2.head
  
웹페이지 정보,웹페이지에 링크될 외부파일들을 링크할 때 사용한다.
  
  3.body
  
  브라우저에 실제로 표시되는 내용을 표기할 때 사용한다.
  
 4.title
  
문서제목을 지정할 때 사용한다.

<>안의 내용이 웹브라우저의 제목 표시줄에 표시된다.
  
   5.meta

문자 인코딩(코드화,암호화),문서의 키워드 및 요약을 작성할 때 사용된다.
  
   6.div

```java
독자적으로 의미를 가지지 않는다.
  
웹페이지 내에 다른 정보들을 묶을때 사용한다.
  
(같은 역할을 하는 <span>도 있지만 차이가 조금 있다.)
```
   7.a 

 ```java
anchor의 약자(?)로,웹페이지를 다른 웹페이지나 외부 사이트와 연결할때 사용한다.
  
(다른 프로그램으로 치면 하이퍼링크와 비슷한 것이다.)
  
사용할 수 있는 속성 값으로는,
 
 7-0.target : 새 창에서에서 링크를 열때 사용. 
  
 7-1._blank : 새로운 창에서 링크를 열때 사용.
  
 7-2._self : 현재 창에서 링크를 열때 사용.

 7-3._parent : 현재 화면을 불러낸 탭에서 링크를 열때 사용.
  
 7-4._top : 최상위 탭에서 링크를 열때 사용.
  
 7-5._title : 링크에 커서를 올렸을 때 나오는 설명을 표시.
  
 7-6._id : 같은 페이지 내에서 이동할 때 사용.
  ``` 
  
  8.script
  
  코드를 삽입할때 사용한다.(보통 자바스크립트 코드를 넣을때 사용된다.)
  
    9.link
  
  외부파일을 연결할 때 사용한다.
  
   10.img
  ```java
  이미지를 삽입할 때 사용한다.
  
  이미지 삽입 방법에는 두 가지가 있다.
  
  1.이미지를 다운로드해 파일경로를 삽입하는 방법
  
  2.다른 페이지의 주소를 복사해서 삽입하는 방법
  ```
  
  11.p
  
  단락을 나눌때 사용한다.
  
  12.ul 
  
  순서가 없는 list
  
   13.ol
  
  순서가 있는 list
  
 14.li
  
  ul과 ol내에서 각 항목을 나열할 때 사용
    
    
  15.style
    
    스타일 정보를 정의할 때 사용한다.
    
    (head와 /head사이에서 정의해야한다.)
    
   
    
   16.br
    
    줄을 바꿀때 사용한다.
    
    
    
   17.hn
    
    h1에서 h2로 정의되는 제목을 작성할 때 사용한다.
      
    (h1에서 h2로 갈수록 글자크기가 작아진다.)
      
    
      
      
   18.input
      
      웹페이지 내에서 사용자가 정보를 입력받아야할때 사용한다.
    
      
   19.form
     
      form을 생성할 때 사용한다.
      
      
   20.inframe
      
      외부페이지를 삽입할 때 사용한다.
      
      
   21.nav
      
      다른 사이트로 연결하는 링크를 작성할 때 사용한다.
      
      
   22.strong
      
      중요한 내용을 강조할 때 사용한다.
      
      
 23.footer
        
  제작정보와 저작권 경보를 작성할 때 사용한다.
      
      
   24.button
      
      form의 요소 중 하나로,버튼을 누름으로써 입력한 값이 전송되는 등
      다양한 경우에 이용된다.
  
      
      
  26.i
     
   문자의 기울임 정도를 조절할 때 사용한다.
      
  
  
   27.b
      
   bold의 약자,문자를 진하게할 때 사용한다. 
      
 
  
  
   28.aside
      
  본문 이외의 내용(광고,링크 등)을 표시할 때 사용된다.    
      
    
  
출처:https://pridiot.tistory.com/6
