---
layout: post
title: 스파르타코딩클럽 웹개발 종합반 - 1주차
subtitle: 1-2
tags: [CSS]
comments: true
---

## **CSS 기초**

- 1) HTML 부모-자식 구조 살펴보기
    
    <aside>
    👉 html 태그는, "누가 누구 안에 있느냐"를 이해하는 것이 가장 중요. 나를 감싸고 있는 태그가 바뀌면, 그 안의 내용물도 모두 영향을 받는다.
    
    </aside>
    
    - 빨간색 div 안에, 초록색/파란색 div가 들어있습니다. 아래와 같은 상황에서 빨간색 div를 가운데로 옮기면, 내용물인 초록/파란 div도 모두 함께 이동하겠죠!
    - 즉, 박스를 옮기면 안의 내용물도 함께 옮겨지는 것과 같은 원리입니다.
    - 같은 원리로, 초록 div의 글씨색을 바꾸면, 나는버튼1의 글씨색도 바뀐답니다!
        
![CSS](https://teamsparta.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F0aa008bc-3f75-4e6a-a9a2-03eaa86551ba%2FUntitled.png?table=block&id=9c3db3aa-db2f-4e59-acbf-3c4098c99dcf&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=1620&userId=&cache=v2)
        
- 2) CSS 기초
    - CSS는 어떻게 사용하나요?
        
        <aside>
        👉 <head> ~ </head> 안에 <style> ~ </style> 로 공간을 만들어 작성합니다.
        아래 코드를 통해 간단한 사용 방법을 알아봅니다.
        
        mytitle라는 클래스를 가리킬 때, .mytitle { ... } 라고 써줘야 하는 것을 꼭! 기억하세요!
        
        </aside>
        
    - 모든 CSS들을 다 알 수는 없겠죠~~ 오늘 쓰는 것만 알아도 굿!
    나머지는 검색해서 쓰시면 된답니다~!
        
        <aside>
        👉 배경관련
        background-color
        background-image
        background-size
        
        사이즈
        width
        height
        
        폰트
        font-size
        font-weight
        font-family
        color
        
        간격
        margin
        padding
        
        </aside>
        

## **06. 자주 쓰이는 CSS 연습하기 (1)**

- 1) 자주 쓰이는 CSS 연습하기
    
    <aside>
    👉 [연습할 것들]
    h1, h5, background-image, background-size, background-position
    color, width, height, border-radius, margin, padding
    
    </aside>
    
    - 튜터와 함께 아래와 같은 화면을 만들어볼까요?
        
        ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4aafd1d6-0983-41db-8c99-c25056413267/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4aafd1d6-0983-41db-8c99-c25056413267/Untitled.png)
        
        <aside>
        💡 margin과 padding      ( → 헷갈리지 말기!)
         - margin은 바깥 여백을, padding은 내 안쪽 여백을
         - div에 색깔을 넣고, 직접 사용해서 차이를 비교해보세요!
        
        </aside>
        
        - **[코드스니펫] 이미지URL**
            
            ```html
            [https://www.ancient-origins.net/sites/default/files/field/image/Agesilaus-II-cover.jpg](https://www.ancient-origins.net/sites/default/files/field/image/Agesilaus-II-cover.jpg)
            ```
            
        
        ```html
        <!DOCTYPE html>
        <html lang="en">
        
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>스파르타코딩클럽 | 로그인페이지</title>
            <style>
                .mytitle {
                    color: white;
                    width: 300px;
                    height: 200px;
                    background-image: url('https://www.ancient-origins.net/sites/default/files/field/image/Agesilaus-II-cover.jpg');
                    background-position: center;
                    background-size: cover;
                    
                    border-radius: 10px;
                    text-align: center;
                    padding-top: 40px;
                }
            </style>
        </head>
        
        <body>
            <div class="mytitle">
                <h1>로그인 페이지</h1>
                <h5>아이디, 비밀번호를 입력해주세요</h5>
            </div>
            <div>
                <p>
                    ID: <input type="text" />
                </p>
                <p>
                    PW: <input type="password" />
                </p>
            </div>
            <button>로그인하기</button>
        </body>
        </body>
        
        </html>
        ```
        
    

## **07. 자주 쓰이는 CSS 연습하기 (2)**

- 만들어둔 로그인 화면을 가운데로 가져오려면?
    
    <aside>
    👉 width를 주고, margin: auto를 사용하자!
    그래도 안되면? display:block을 추가!
    
    </aside>
    
    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/32e462d8-8894-4bb5-9375-72e1d4285c97/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/32e462d8-8894-4bb5-9375-72e1d4285c97/Untitled.png)
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>스파르타코딩클럽 | 로그인페이지</title>
        <style>
            .mytitle {
                color: white;
                width: 300px;
                height: 200px;
                background-image: url('https://www.ancient-origins.net/sites/default/files/field/image/Agesilaus-II-cover.jpg');
                background-position: center;
                background-size: cover;
    
                border-radius: 10px;
                text-align: center;
                padding-top: 40px;
            }
    
            .wrap {
                margin: 10px auto;
                width: 300px;
            }
        </style>
    </head>
    
    <body>
        <div class="wrap">
            <div class="mytitle">
                <h1>로그인 페이지</h1>
                <h5>아이디, 비밀번호를 입력해주세요</h5>
            </div>
            <div>
                <p>
                    ID: <input type="text" />
                </p>
                <p>
                    PW: <input type="password" />
                </p>
            </div>
            <button>로그인하기</button>
        </div>
    </body>
    </body>
    
    </html>
    ```
    

##
