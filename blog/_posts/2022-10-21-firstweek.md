---
layout: post
title: 스파르타코딩클럽 웹개발 종합반 1주차
subtitle: 1-1
tags: [HTML, CSS]
comments: true
---

## **HTML, CSS 기본 내용**

- 1) HTML과 CSS의 개념
    
    <aside>
    👉 HTML은 뼈대, CSS는 꾸미기!
    
    </aside>
    
- 2) HTML 기초
    
    <aside>
    👉 HTML은 크게 head와 body로 구성.
    
    </aside>
    
    - head안에는 페이지의 속성 정보를, body안에는 페이지의 내용을 담습니다.
    - head 안에 들어가는 대표적인 요소들: meta, script, link, title 등
        
    - body 안에 들어가는 대표적인 요소들!
        - **HTML기초**
            
            ```html
            <!DOCTYPE html>
            <html lang="en">
            
            <head>
                <meta charset="UTF-8">
                <meta name="viewport" content="width=device-width, initial-scale=1.0">
                <title>HTML기초 | HTML 기초</title>
            </head>
            
            <body>
                <!-- 구역을 나누는 태그들 -->
                <div>나는 구역을 나누죠</div>
                <p>나는 문단이에요</p>
                <ul>
                    <li> bullet point!1 </li>
                    <li> bullet point!2 </li>
                </ul>
            
                <!-- 구역 내 콘텐츠 태그들 -->
                <h1>h1은 제목을 나타내는 태그입니다. 페이지마다 하나씩 꼭 써주는 게 좋아요. 그래야 구글 검색이 잘 되거든요.</h1>
                <h2>h2는 소제목입니다.</h2>
                <h3>h3~h6도 각자의 역할이 있죠. 비중은 작지만..</h3>
                <hr>
                span 태그입니다: 특정 <span style="color:red">글자</span>를 꾸밀 때 써요
                <hr>
                a 태그입니다: <a href="http://naver.com/"> 하이퍼링크 </a>
                <hr>
                img 태그입니다: <img src="https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png" />
                <hr>
                input 태그입니다: <input type="text" />
                <hr>
                button 태그입니다: <button> 버튼입니다</button>
                <hr>
                textarea 태그입니다: <textarea>나는 무엇일까요?</textarea>
            </body>
            
            </html>
            ```
            
## **간단한 로그인 페이지 만들어보기**

- 1) ✍간단한 로그인 페이지 만들기

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>로그인페이지</title>
</head>
<body>
    <h1>로그인 페이지</h1>
    <p>ID: <input type="text"/></p>
    <p>PW: <input type="text"/></p>
    <button>로그인하기</button>
</body>
</html>

<aside>
- **로그인HTML**
    
</aside>

        ```html
        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <title>로그인페이지</title>
        </head>
        <body>
            <h1>로그인 페이지</h1>
            <p>ID: <input type="text"/></p>
            <p>PW: <input type="text"/></p>
            <button>로그인하기</button>
        </body>
        </html>
        ```
