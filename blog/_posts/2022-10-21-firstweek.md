---
layout: post
title: 스파르타코딩클럽 웹개발 종합반 1주차
subtitle: 1-1
tags: [HTML, CSS]
comments: true
---

## **03. HTML, CSS 기본 내용**

<aside>
💡 바탕화면에 `sparta` 폴더 → `frontend` 폴더를 만들고 시작할게요!

</aside>

- 1) HTML과 CSS의 개념
    
    <aside>
    👉 HTML은 뼈대, CSS는 꾸미기!
    
    </aside>
    
    - HTML은 구역과 텍스트를 나타내는 코드로, CSS는 잡은 구역을 꾸며주는 것으로 생각합니다. HTML 내 style 속성으로 꾸미기를 할 수 있지만, 긴 세월동안 이것을 한데 모아 볼 수 있는 CSS 파일이 탄생하게 되었습니다. HTML 코드 내에 CSS 파일을 불러와서 적용합니다.
    - 또한 CSS를 잘 사용할 줄 아는 것과, '예쁘게' 만드는 것은 다른 영역이기 때문에(붓을 잡을 줄 아는 것과 그림을 잘 그릴 줄 아는 것의 차이), 많은 경우 웹디자이너나 퍼블리셔에게 의존하게 됩니다.
- 2) HTML 기초
    
    <aside>
    👉 HTML은 크게 head와 body로 구성된답니다.
    
    </aside>
    
    - head안에는 페이지의 속성 정보를, body안에는 페이지의 내용을 담습니다.
    - head 안에 들어가는 대표적인 요소들: meta, script, link, title 등
        
        <aside>
        👉 페이지의 속성을 정의하거나, 필요한 스크립트들을 부릅니다. 즉, 눈에 안 보이는 필요한 것들을 담는 것. 나중에 body 작업을 하면서 필요한 정보들을 넣어보겠습니다.
        
        </aside>
        
    - body 안에 들어가는 대표적인 요소들!
        - **[코드스니펫] HTML기초**
            
            ```html
            <!DOCTYPE html>
            <html lang="en">
            
            <head>
                <meta charset="UTF-8">
                <meta name="viewport" content="width=device-width, initial-scale=1.0">
                <title>스파르타코딩클럽 | HTML 기초</title>
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
            
        
        <aside>
        👉 이 외에도 아주 많으며, 개발자들도 모두 외우고 있지 않습니다. 필요할 때마다 찾아서 넣어보세요!
        
        </aside>
        
        <aside>
        👉 **잠깐! 정렬의 중요성**
        코드의 정렬이 제대로 되어있지 않으면, 코드의 생김새를 파악할 수 없어 오류를 해결하기가 무척 어려워집니다. Pycharm에서 **ctrl+alt+L** (맥은 cmd+alt+L) 로 자동정렬 기능을 사용해보세요.
        
        </aside>
        

## **04. Quiz_간단한 로그인 페이지 만들어보기**

- 1) ✍간단한 로그인 페이지 만들기
    
    <aside>
    🔥 앞으로 실습이 필요한 부분이 나오면 "✍"모양으로 알려줄게요!
    퀴즈설명 영상을 먼저 보고 → 정해진 시간동안 혼자 한다음 → 함께하기 영상을 보세요!
    
    </aside>
    
    - Q. 퀴즈설명
        - 모습 보기
            
            ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6a2b76fd-9264-41c0-b0cc-2a44ad472624/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6a2b76fd-9264-41c0-b0cc-2a44ad472624/Untitled.png)
            
        
        <aside>
        👻 힌트: 위의 HTML기초에서 봤던 코드들을 적절히 조합해보세요!
        ctrl+c,v 신공을 사용해보세요!
        
        </aside>
        
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
        
    - A. 함께하기(완성본)
        
        <aside>
        💡 어때요, 할만했나요? 다만 조금씩 다른 방법으로 해결하셨더라도,
        다음 강의 진행을 위해 아래 코드를 복사→붙여넣기 해주세요!
        
        </aside>
        
        - **[코드스니펫] 로그인HTML**
            
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
            
    

## **05. CSS 기초**

- 1) HTML 부모-자식 구조 살펴보기
    
    <aside>
    👉 html 태그는, "누가 누구 안에 있느냐"를 이해하는 것이 가장 중요합니다. 나를 감싸고 있는 태그가 바뀌면, 그 안의 내용물도 모두 영향을 받지요!
    
    </aside>
    
    - 빨간색 div 안에, 초록색/파란색 div가 들어있습니다. 아래와 같은 상황에서 빨간색 div를 가운데로 옮기면, 내용물인 초록/파란 div도 모두 함께 이동하겠죠!
    - 즉, 박스를 옮기면 안의 내용물도 함께 옮겨지는 것과 같은 원리입니다.
    - 같은 원리로, 초록 div의 글씨색을 바꾸면, 나는버튼1의 글씨색도 바뀐답니다!
        
        ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0aa008bc-3f75-4e6a-a9a2-03eaa86551ba/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0aa008bc-3f75-4e6a-a9a2-03eaa86551ba/Untitled.png)
        
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
    

## **08. 폰트, 주석, 파일분리**

- 1) 구글 웹폰트 입히기
    - 구글 웹폰트
        - **[코드스니펫] 구글웹폰트**
            
            ```python
            [https://fonts.google.com/?subset=korean](https://fonts.google.com/?subset=korean)
            ```
            
        
        (1) 마음에 드는 폰트를 클릭합니다.
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3206d560-88dc-4251-91ad-810531d49dd4/Untitled.png)
        
        (2) [ + Select this style ]을 클릭합니다.
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3a9f3121-f16a-4df4-8746-5f43b9d9c966/Untitled.png)
        
        (3) 우측 상단의 모음 아이콘을 클릭합니다.
        
        ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/652c2629-e89c-41ee-a411-251ab3babe6c/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/652c2629-e89c-41ee-a411-251ab3babe6c/Untitled.png)
        
        (4) Embed 탭을 클릭합니다.
        
        ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/29b811c0-5699-4135-b4e4-7e7076e74236/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/29b811c0-5699-4135-b4e4-7e7076e74236/Untitled.png)
        
        (5) link 태그를 복사해서 <head> ~ </head>사이에, CSS를 복사해서 <style> ~ </style> 사이에 넣습니다.
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/216f26e9-7bad-4209-b002-d9fdc00ccc41/Untitled.png)
        
    - Jua라는 폰트를 예제로 추가해보면, 아래와 같은 코드를 복사하면 됩니다.
        
        ```html
        <!-- HTML에 이 부분을 추가하고 -->
        <link href="https://fonts.googleapis.com/css2?family=Jua&display=swap" rel="stylesheet">
        ```
        
        ```css
        /* CSS에 이 부분을 추가하면 완성! */
        * {
        	font-family: 'Jua', sans-serif;
        }
        ```
        
- 2) 꿀팁! 주석 달기
    
    <aside>
    👉 주석은 언제 사용하나요?
    1) 필요없어진 코드를 삭제하는 대신 임시로 작동하지 못하게 하고 싶을 때
    2) 코드에 대한 간단한 설명을 붙여두고 싶을 때 사용합니다.
    
    주석을 붙여놓으면, 브라우저/컴퓨터가 읽지 않아요.
    즉, 개발자 본인 또는 동료를 위해 붙여두는 것!
    
    </aside>
    
    - 단축키: 주석처리하고 싶은 라인들을 선택 → **ctrl(또는 command) + /  (슬래시)**
- 3) CSS 파일 분리
    
    <aside>
    👉 <style> ~ </style> 부분이 너무 길어지면, 보기가 어렵겠죠? 이럴 땐 아래와 같이 파일을 분리해둘 수 있습니다.
    
    지금은 css가 간단하고, 한 파일에서 보는 게 편하기 때문에 일단은 패스!
    
    </aside>
    
    <aside>
    🔥 **이 부분은 튜터님만 혼자하면서 보여드릴게요! 여러분은 구경만!**
    
    </aside>
    
    ```html
    <!-- style.css 파일을 같은 폴더에 만들고, head 태그에서 불러오기 -->
    <link rel="stylesheet" type="text/css" href = "(css파일이름).css">
    ```
    

## 09**. 부트스트랩, 예쁜 CSS 모음집**

- 1) bootstrap이란?
    - 부트스트랩이란? 예쁜 CSS를 미리 모아둔 것 (CSS를 다룰 줄 아는 것과, 미적 감각을 발휘하여 예쁘게 만드는 것은 다른 이야기이기 때문에, 현업에서는 미리 완성된 부트스트랩을 가져다 쓰는 경우가 많습니다.)
- 2) bootstrap - 시작 템플릿
    
    <aside>
    👉 남이 미리 작성한 CSS를 내 HTML 파일에 적용한다는 점에서, bootstrap 적용은 CSS 파일 분리와 원리가 동일합니다. (아까 튜터님의 시범을 기억하시죠!)
    다만, CSS의 파일이 인터넷 어딘가에 있다는 점이 다를 뿐입니다.
    
    </aside>
    
    - 아래 파일을 복사해서 새로운 HTML 파일을 하나 만들고, 시작해보아요
    - **[코드스니펫] 부트스트랩 시작 템플릿**
        
        ```html
        <!doctype html>
        <html lang="en">
        
        <head>
            <meta charset="utf-8">
            <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
        
            <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
                integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
            <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
                integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
                crossorigin="anonymous"></script>
        
            <title>스파르타코딩클럽 | 부트스트랩 연습하기</title>
        </head>
        
        <body>
            <h1>이걸로 시작해보죠!</h1>
        </body>
        
        </html>
        ```
        
    - **[코드스니펫] 부트스트랩 컴포넌트 5.0**
        
        ```html
        https://getbootstrap.com/docs/5.0/components/buttons/
        ```
        
    
    <aside>
    👉 예쁜 버튼이 생겼습니다! (부트스트랩이 미리 css를 작성해뒀기 때문)
    즉, btn 과, btn-primary 라는 class를 미리 정의해둔 것이죠
    
    </aside>
    
    - <h1>~</h1> 자리 아래 코드를 넣어봅니다.

## 10**. CSS 꿀팁 한번 더 배우기**

- Bootstrap을 쓰기 전에 - CSS 꿀팁 한번 더 배우기!
    
    <aside>
    👉 최종적으로 만들 것 구경하기!
    
    </aside>
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/127e5a66-725a-4995-a0fe-bf1e01e0516d/Untitled.png)
    
    - **[코드스니펫] 상어 배경**
        
        ```csharp
        https://movie-phinf.pstatic.net/20210715_95/1626338192428gTnJl_JPEG/movie_image.jpg
        ```
        
    - **[코드스니펫] 전체 코드**
        
        ```csharp
        <!doctype html>
        <html lang="en">
        
        <head>
            <meta charset="utf-8">
            <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
        
            <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
                integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
            <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
                integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
                crossorigin="anonymous"></script>
        
            <title>스파르타 피디아</title>
        
            <style>
                .mytitle {
                    width: 100%;
                    height: 250px;
        
                    background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://movie-phinf.pstatic.net/20210715_95/1626338192428gTnJl_JPEG/movie_image.jpg');
                    background-position: center;
                    background-size: cover;
        
                    color: white;
        
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    justify-content: center;
                }
                .mytitle > button {
                    width: 200px;
                    height: 50px;
        
                    background-color: transparent;
                    color: white;
        
                    border-radius: 50px;
                    border: 1px solid white;
        
                    margin-top: 10px;
                }
        
                .mytitle > button:hover {
                    border: 2px solid white;
                }
            </style>
        </head>
        
        <body>
            <div class="mytitle">
                <h1>내 생애 최고의 영화들</h1>
                <button>영화 기록하기</button>
            </div>
        </body>
        
        </html>
        ```
        

## 11**. CSS 꿀팁-폰트넣기**

- 폰트 넣기
    
    <aside>
    👉 `Gowun Dodum` 체를 써보겠습니다!
    
    </aside>
    
    - **[코드스니펫] 구글폰트 link**
        
        ```jsx
        <link href="https://fonts.googleapis.com/css2?family=Gowun+Dodum&display=swap" rel="stylesheet">
        ```
        
    - **[코드스니펫] 구글폰트 css**
        
        ```css
        * {
            font-family: 'Gowun Dodum', sans-serif;
        }
        ```
        
    - **[코드스니펫] 이미지 어둡게 하기**
        
        ```csharp
        linear-gradient(0deg, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5))
        ```
        
    - 아래를 찾아 붙여 넣으면 완성!
        
        ```jsx
        <link href="https://fonts.googleapis.com/css2?family=Gowun+Dodum&display=swap" rel="stylesheet">
        ```
        
        ```css
        * {
            font-family: 'Gowun Dodum', sans-serif;
        }
        ```
        

## 12**. 본격 부트스트랩 써보기**

- 1) Bootstrap 본격적으로 써보기
    
    <aside>
    👉 남이 만들어 둔 것을 쓸 때는 잘 찾아다가 조금씩만 고쳐서 쓰는 게 답입니다!
    
    </aside>
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e44204ca-28c5-4333-82b3-401badc3d69f/Untitled.png)
    
    1. 카드 복사해서 붙여넣기
        - Card 카테고리에서 여러개 있는 Card 를 클릭!
    2. 이미지 넣고, 개수 조절하기
        - `row-cols-md-3` → `row-cols-md-4` 로 바꾸기
        - **[코드스니펫] 포스터이미지**
            
            ```csharp
            https://movie-phinf.pstatic.net/20210728_221/1627440327667GyoYj_JPEG/movie_image.jpg
            ```
            
    3. 별 넣고, 코멘트 달기
        - <p> 태그를 활용합니다. 코멘트는 class를 줘서 회색 글씨로!
        - **[코드스니펫] 별 표기**
            
            ```csharp
            ⭐⭐⭐
            ```
            
        - **[코드스니펫] 꿀팁 - 이모티콘 모음**
            
            ```csharp
            https://kr.piliapp.com/facebook-symbols/
            ```
            

## **13. Quiz_포스팅박스를 완성하기!**

- 1) ✍포스팅 박스를 넣어보기 (20분)
    - Q. 퀴즈설명: 아래 모양을 만들어보세요!
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0bce3fe1-e9df-4259-a3a7-a1cdfffd147f/Untitled.png)
        
        <aside>
        👻 힌트: 아래 순서대로 만들어보세요!
        
        </aside>
        
        1. 우선 큰 박스 먼저 만들기 (함께)
            
            → 그림자 효과: `box-shadow: 0px 0px 3px 0px gray;`
            
            → 안쪽으로 띄우기: `padding: 20px;`
            
        2. 영화 URL
            
            → Forms 의 Floating Labels 참고
            
        3. 별점 박스
            
            → Input group의 Custom forms 참고
            
        4. 코멘트 URL
            
            → Forms 의 Floating Labels의 Textareas 참고
            
        5. 기록하기, 닫기 버튼
            
            → Button 두 개를 묶을 div를 만들어 `display:flex` 주기 (네 줄!)
            
            → Buttons 참고
            
    - A. 함께하기(완성본)
        - **[코드스니펫] 포스팅박스까지(완성)**
            
            ```html
            <!doctype html>
            <html lang="en">
            
            <head>
                <meta charset="utf-8">
                <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
            
                <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
                      integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
                <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
                <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
                        integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
                        crossorigin="anonymous"></script>
            
                <title>스파르타 피디아</title>
            
                <link href="https://fonts.googleapis.com/css2?family=Gowun+Dodum&display=swap" rel="stylesheet">
            
                <style>
                    * {
                        font-family: 'Gowun Dodum', sans-serif;
                    }
            
                    .mytitle {
                        width: 100%;
                        height: 250px;
            
                        background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://movie-phinf.pstatic.net/20210715_95/1626338192428gTnJl_JPEG/movie_image.jpg');
                        background-position: center;
                        background-size: cover;
            
                        color: white;
            
                        display: flex;
                        flex-direction: column;
                        align-items: center;
                        justify-content: center;
                    }
            
                    .mytitle > button {
                        width: 200px;
                        height: 50px;
            
                        background-color: transparent;
                        color: white;
            
                        border-radius: 50px;
                        border: 1px solid white;
            
                        margin-top: 10px;
                    }
            
                    .mytitle > button:hover {
                        border: 2px solid white;
                    }
            
                    .mycomment {
                        color: gray;
                    }
            
                    .mycards {
                        margin: 20px auto 0px auto;
                        width: 95%;
                        max-width: 1200px;
                    }
            
                    .mypost {
                        width: 95%;
                        max-width: 500px;
                        margin: 20px auto 0px auto;
                        padding: 20px;
                        box-shadow: 0px 0px 3px 0px gray;
                    }
            
                    .mybtns {
                        display: flex;
                        flex-direction: row;
                        align-items: center;
                        justify-content: center;
            
                        margin-top: 20px;
                    }
                    .mybtns > button {
                        margin-right: 10px;
                    }
                </style>
            </head>
            
            <body>
            <div class="mytitle">
                <h1>내 생애 최고의 영화들</h1>
                <button>영화 기록하기</button>
            </div>
            <div class="mypost">
                <div class="form-floating mb-3">
                    <input type="email" class="form-control" id="floatingInput" placeholder="name@example.com">
                    <label for="floatingInput">영화URL</label>
                </div>
                <div class="input-group mb-3">
                    <label class="input-group-text" for="inputGroupSelect01">별점</label>
                    <select class="form-select" id="inputGroupSelect01">
                        <option selected>-- 선택하기 --</option>
                        <option value="1">⭐</option>
                        <option value="2">⭐⭐</option>
                        <option value="3">⭐⭐⭐</option>
                        <option value="4">⭐⭐⭐⭐</option>
                        <option value="5">⭐⭐⭐⭐⭐</option>
                    </select>
                </div>
                <div class="form-floating">
                    <textarea class="form-control" placeholder="Leave a comment here" id="floatingTextarea2"
                              style="height: 100px"></textarea>
                    <label for="floatingTextarea2">코멘트</label>
                </div>
                <div class="mybtns">
                    <button type="button" class="btn btn-dark">기록하기</button>
                    <button type="button" class="btn btn-outline-dark">닫기</button>
                </div>
            </div>
            <div class="mycards">
                <div class="row row-cols-1 row-cols-md-4 g-4">
                    <div class="col">
                        <div class="card h-100">
                            <img src="https://movie-phinf.pstatic.net/20210728_221/1627440327667GyoYj_JPEG/movie_image.jpg"
                                 class="card-img-top" alt="...">
                            <div class="card-body">
                                <h5 class="card-title">영화 제목이 들어갑니다</h5>
                                <p class="card-text">여기에 영화에 대한 설명이 들어갑니다.</p>
                                <p>⭐⭐⭐</p>
                                <p class="mycomment">나의 한줄 평을 씁니다</p>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="card h-100">
                            <img src="https://movie-phinf.pstatic.net/20210728_221/1627440327667GyoYj_JPEG/movie_image.jpg"
                                 class="card-img-top" alt="...">
                            <div class="card-body">
                                <h5 class="card-title">영화 제목이 들어갑니다</h5>
                                <p class="card-text">여기에 영화에 대한 설명이 들어갑니다.</p>
                                <p>⭐⭐⭐</p>
                                <p class="mycomment">나의 한줄 평을 씁니다</p>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="card h-100">
                            <img src="https://movie-phinf.pstatic.net/20210728_221/1627440327667GyoYj_JPEG/movie_image.jpg"
                                 class="card-img-top" alt="...">
                            <div class="card-body">
                                <h5 class="card-title">영화 제목이 들어갑니다</h5>
                                <p class="card-text">여기에 영화에 대한 설명이 들어갑니다.</p>
                                <p>⭐⭐⭐</p>
                                <p class="mycomment">나의 한줄 평을 씁니다</p>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="card h-100">
                            <img src="https://movie-phinf.pstatic.net/20210728_221/1627440327667GyoYj_JPEG/movie_image.jpg"
                                 class="card-img-top" alt="...">
                            <div class="card-body">
                                <h5 class="card-title">영화 제목이 들어갑니다</h5>
                                <p class="card-text">여기에 영화에 대한 설명이 들어갑니다.</p>
                                <p>⭐⭐⭐</p>
                                <p class="mycomment">나의 한줄 평을 씁니다</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            </body>
            
            </html>
            ```
            
- 2) 약간의 모바일 처리를 해두기
    
    <aside>
    👉 모바일에서는 "가로 사이즈"가 가장 문제랍니다! 😎
    
    </aside>
    
    - 어디서나 500px 로 맞춰라 (width: 500px)
        
        `대신에,`
        
    - 화면 폭 500px 전에는 95%로 맞추다가, 넘으면 500px으로 보여줘 라고 할 수 있다면?
        
        ```css
        width: 95%;
        max-width: 500px;
        ```
        
    

## **14. Javascript 맛보기**

- 1) 자바스크립트란?
    - 프로그래밍 언어 중 하나로, 브라우저가 알아들을 수 있는 언어입니다.
        
        <aside>
        👉 이론 설명 때, 클라이언트가 서버에 요청하면, 서버가 클라이언트에게
        HTML+CSS+Javascript를 준다고 했던 것, 기억하시나요?
        
        </aside>
        
        <aside>
        👉 [잠깐 상식!]
        
        Q. 왜 브라우저는 Javascript만 알아들어요? HTML안에다 파이썬, Java 같은 언어를 써서 주면 안되나요?
        
        A. 불가능한 이야기는 아닙니다. 다만, 이 "역사적인 이유 & 이미 만들어진 표준"이기 때문에, 모든 브라우저는 기본적으로 Javascript를 알아듣게 설계되어있고, 모든 웹서버는 HTML+CSS+Javascript를 주게 되어있죠.
        
        </aside>
        
    - Java와 Javascript는 어떤 차이가 있나요?
        
        <aside>
        👉 인도와 인도네시아..
        바다와 바다코끼리..
        
        아무 관련 없습니다.
        
        </aside>
        
- 2) 자바스크립트 기초
    - 처음 프로그래밍 언어를 배우면 생소한 부분도 존재하기에, 다음 주에 본격적으로 하기 전에! 오늘 먼저 맛보기를 해보겠습니다.
        
        <aside>
        👉 일단 따라쓰기!를 통해,
        자바스크립트가 HTML과 어떻게 연동되는지 알아보겠습니다.
        
        </aside>
        
- 3) 자바스크립트 - HTML 연결. 버튼을 클릭하면 경고창이 뜨게하기
    - 함수를 만들어두기
        
        ```jsx
        function hey(){
        	alert('안녕!');
        }
        ```
        
        <aside>
        👉 <head> ~ </head> 안에 <script> ~ </script> 로 공간을 만들어 작성합니다.
        
        <script> ~ </script> 내에 자바스크립트를 작성하는 것이죠
        아래 코드를 통해 간단한 사용방법을 알아봅니다.
        
        </aside>
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ea58b70a-9cee-4de8-816e-b806e01e96fb/Untitled.png)
        
    - 버튼에 함수를 연결하기. 버튼을 누르면 함수가 불립니다.
        
        ```html
        <button onclick="hey()">영화 기록하기</button>
        ```
        

## **15. Javascript 기초 문법 배우기(1)**

- 1) 본격적으로 문법을 배워볼까요?
    
    <aside>
    👉 1주차엔 문법을 배우고, 2주차에 이리저리 연습을 많~이 할거예요!
    
    </aside>
    
    - [크롬 개발자도구]를 열어서, console 탭에 작성합니다!
        
        <aside>
        👉 그냥 쉽게, "마우스 오른쪽 클릭 → 검사 → console"도 가능!
        
        크롬 개발자도구 콘솔창은 어떤 의미?
        > 띄워놓은 페이지에서 빠르게 자바스크립트를 테스트해볼 수 있게, 개발자들을 위해 만들어둔 도구입니다. 새로고침하면 모두 사라진다는 사실!
        
        </aside>
        
        - 윈도우: F12
        - 맥: alt(option) + command + i
        - console.log(변수)
            
            ```jsx
            --
            console.log(변수) 는, 콘솔 창에 괄호 안의 값을 출력해줍니다.
            개발자가 결과값을 보기 편하도록!
            
            console.log(변수1,변수2) 로 여러 변수를 한번에 출력할 수도 있어요.
            아래를 복사해서 붙여넣어보세요.
            
            console.log("Hello World!");
            ```
            
    - 변수 & 기본연산
        - 변수 대입( a = 2 )의 의미: "오른쪽에 있는 것을 왼쪽에 넣는 것!"
        (2를 a라는 변수에 넣는다)
        - let으로 변수를 선언합니다.
            
            ```jsx
            let num = 20
            num = 'Bob'
            
            // 변수는 값을 저장하는 박스예요.
            // 한 번 선언했으면, 다시 선언하지 않고 값을 넣습니다.
            ```
            
        - 사칙연산, 그리고 문자열 더하기가 기본적으로 가능합니다.
            
            ```jsx
            let a = 1
            let b = 2
            
            a+b // 3
            a/b // 0.5
            
            let first = 'Bob'
            let last = 'Lee'
            
            first+last // 'BobLee'
            
            first+' '+last // 'Bob Lee'
            
            first+a // Bob1 -> 문자+숫자를 하면, 숫자를 문자로 바꾼 뒤 수행합니다.
            ```
            
        - 변수명은 아무렇게나?
            
            ```jsx
            let first_name = 'bob' // snake case라고 합니다.
            
            또는,
            
            let firstName = 'bob' // camel case라고 합니다. 회사마다 규칙이 있죠.
            
            과 같이, 쉽게 알아볼 수 있게 쓰는 게 중요합니다.
            다른 특수문자 또는 띄워쓰기는 불가능합니다!
            ```
            

## **16. Javascript 기초 문법 배우기(2)**

- 리스트 & 딕셔너리
    - 리스트: 순서를 지켜서 가지고 있는 형태입니다.
        
        ```jsx
        let a_list = []  // 리스트를 선언. 변수 이름은 역시 아무렇게나 가능!
        
        // 또는,
        
        let b_list = [1,2,'hey',3] // 로 선언 가능
        
        b_list[1] // 2 를 출력
        b_list[2] // 'hey'를 출력
        
        // 리스트에 요소 넣기
        b_list.push('헤이')
        b_list // [1, 2, "hey", 3, "헤이"] 를 출력
        
        // 리스트의 길이 구하기
        b_list.length // 5를 출력
        ```
        
    - 딕셔너리: 키(key)-밸류(value) 값의 묶음
        
        ```jsx
        let a_dict = {}  // 딕셔너리 선언. 변수 이름은 역시 아무렇게나 가능!
        
        // 또는,
        
        let b_dict = {'name':'Bob','age':21} // 로 선언 가능
        b_dict['name'] // 'Bob'을 출력
        b_dict['age'] // 21을 출력
        
        b_dict['height'] = 180 // 딕셔너리에 키:밸류 넣기
        b_dict // {name: "Bob", age: 21, height: 180}을 출력
        ```
        
    - 리스트와 딕셔너리의 조합
        
        ```jsx
        names = [{'name':'bob','age':20},{'name':'carry','age':38}]
        
        // names[0]['name']의 값은? 'bob'
        // names[1]['name']의 값은? 'carry'
        
        new_name = {'name':'john','age':7}
        names.push(new_name)
        
        // names의 값은? [{'name':'bob','age':20},{'name':'carry','age':38},{'name':'john','age':7}]
        // names[2]['name']의 값은? 'john'
        ```
        
    - 왜 필요할까요?
        
        <aside>
        💡 **순서를 표시할 수 있고, 정보를 묶을 수 있습니다.**
        
        앞에서 언급한 <스파르타과일가게>가 정말 잘 되어서 전국에서 손님이 찾아오고 있습니다. 대기표를 작성하기 위해서 온 순서대로 이름,  휴대폰 번호를 적도록 하였는데요. 변수만을 사용한 모습은 다음과 같습니다.
        
        let customer_1_name = '김스파';
        let customer_1_phone = '010-1234-1234';
        let customer_2_name = '박르탄';
        let customer_2_phone = '010-4321-4321';
        ...(알아보기 힘듭니다.)
        
        👉딕셔너리를 활용한다면 다음과 같이 고객 별로 정보를 묶을 수 있습니다.
        let customer_1 = {'name': '김스파', 'phone': '010-1234-1234'};
        let customer_2 = {'name': '박르탄', 'phone': '010-4321-4321'};
        
        👉그리고 순서를 나타내기 위해 리스트를 사용하면, 이렇게나 깔끔해집니다.
        let customer = [
            {'name': '김스파', 'phone': '010-1234-1234'},
            {'name': '박르탄', 'phone': '010-4321-4321'}
        ]
        
        ✅보기에도 깔끔해지고, 다루기도 쉬워지고, 고객이 새로 한 명 더 오더라도 .push 함수를 이용해 간단하게 대응할 수 있습니다.
        
        </aside>
        
- 기본 함수들
    - 사칙연산 외에도, 기본적으로 제공하는 여러 함수들이 존재합니다.
        
        <aside>
        👉 왠지 이건 있을 것 같은데?(예 - 특정 문자를 바꾸고 싶다 등) 싶으면 직접 만들지 말고 **구글에 먼저 찾아보세요!**
        
        </aside>
        
        ```jsx
        **예를 들면, '나눗셈의나머지'를 구하고 싶은 경우**
        
        let a = 20
        let b = 7
        
        a % b = 6
        ```
        
        ```jsx
        **또, 특정 문자로 문자열을 나누고 싶은 경우**
        
        let myemail = 'sparta@gmail.com'
        
        let result = myemail.split('@') // ['sparta','gmail.com']
        
        result[0] // sparta
        result[1] // gmail.com
        
        let result2 = result[1].split('.') // ['gmail','com']
        
        result2[0] // gmail -> 우리가 알고 싶었던 것!
        result2[1] // com
        
        myemail.split('@')[1].split('.')[0] // gmail -> 간단하게 쓸 수도 있다!
        ```
        

## **17. Javascript 기초 문법 배우기(3)**

- 1) 더 본격적으로 문법을 배워볼까요!
    - 함수
        - 기본 생김새
            
            ```jsx
            // 만들기
            function 함수이름(필요한 변수들) {
            	내릴 명령들을 순차적으로 작성
            }
            // 사용하기
            함수이름(필요한 변수들);
            ```
            
        - 예시
            
            ```jsx
            // 두 숫자를 입력받으면 더한 결과를 돌려주는 함수
            function sum(num1, num2) {
            	console.log('숫자', num1, num2);
            	return num1 + num2;
            }
            
            sum(3, 5); // 8
            sum(4, -1); // 3
            ```
            
    - 조건문
        - 20 보다 작으면 작다고, 크면 크다고 알려주는 함수
            
            ```jsx
            function is_adult(age){
            	if(age > 20){
            		alert('성인이에요')
            	} else {
            		alert('청소년이에요')
            	}
            }
            
            is_adult(25)
            ```
            
        - if, else if, else if, else if else
            
            ```jsx
            function is_adult(age){
            	if(age > 20){
            		alert('성인이에요')
            	} else if (age > 10) {
            		alert('청소년이에요')
            	} else {
            		alert('10살 이하!')
            	}
            }
            
            is_adult(12)
            ```
            
    

## **18. Javascript 기초 문법 배우기(4)**

- 반복문
    - 예를 들어 0부터 99까지 출력해야 하는 상황이라면!
        
        ```jsx
        console.log(0)
        console.log(1)
        console.log(2)
        console.log(3)
        console.log(4)
        console.log(5)
        ...
        console.log(99)
        
        // 이렇게 쓰기엔 무리가 있겠죠? 그래서, 반복문이라는 것이 존재합니다!
        ```
        
    - 반복문을 이용하면 아래와 같이 단 세줄로, 출력할 수 있습니다.
        
        ```jsx
        for (let i = 0; i < 100; i++) {
        	console.log(i);
        }
        ```
        
        ```jsx
        for (1. 시작조건; 2. 반복조건; 3. 더하기) {
        	4. 매번실행
        }
        
        1 -> 2체크하고 -> (괜찮으면) -> 4 -> 3
        -> 2체크하고 -> (괜찮으면) -> 4 -> 3
        -> 2체크하고 -> (괜찮으면) -> 4 -> 3
        -> 2체크하고 -> (괜찮으면) -> 4 -> 3
        
        와 같은 순서로 실행됩니다.
        i가 증가하다가 반복조건에 맞지 않으면, 반복을 종료하고 빠져나옵니다.
        ```
        
    - 그러나 위처럼 숫자를 출력하는 경우보다는, 반복문은 주로 리스트와 함께 쓰입니다.
    아래 예시를 볼까요? 일단 아래를 복사 붙여넣기 하고, 함께 코딩해볼게요
        - **[코드스니펫] 반복문 예제1**
            
            ```jsx
            let people = ['철수','영희','민수','형준','기남','동희']
            ```
            
        
        ```jsx
        let people = ['철수','영희','민수','형준','기남','동희']
        
        // 이렇게 하면 리스트의 모든 원소를 한번에 출력할 수 있겠죠?
        // i가 1씩 증가하면서, people의 원소를 차례대로 불러올 수 있게 됩니다.
        for (let i = 0 ; i < people.length ; i++) {
        	console.log(people[i])
        }
        ```
        
    - 리스트도 그냥 리스트가 아닙니다! 딕셔너리가 들어간 리스트와 찰떡이죠
    다시 아래를 복사 붙여넣기 해볼까요?
        - **[코드스니펫] 반복문 예제2**
            
            ```jsx
            let scores = [
            	{'name':'철수', 'score':90},
            	{'name':'영희', 'score':85},
            	{'name':'민수', 'score':70},
              {'name':'형준', 'score':50},
              {'name':'기남', 'score':68},
              {'name':'동희', 'score':30},
            ]
            ```
            
        
        ```jsx
        let scores = [
        	{'name':'철수', 'score':90},
        	{'name':'영희', 'score':85},
        	{'name':'민수', 'score':70},
          {'name':'형준', 'score':50},
          {'name':'기남', 'score':68},
          {'name':'동희', 'score':30},
        ]
        
        for (let i = 0 ; i < scores.length ; i++) {
        	console.log(scores[i]);
        }
        
        // 이렇게 하면 리스트 내의 딕셔너리를 하나씩 출력할 수 있고,
        ```
        
        ```jsx
        for (let i = 0 ; i < scores.length ; i++) {
        	if (scores[i]['score'] < 70) {
        		console.log(scores[i]['name']);
        	}
        }
        
        // 이렇게 하면 점수가 70점 미만인 사람들의 이름만 출력할 수도 있습니다.
        ```
        

## 19**. Javascript 연습하기**

- 1) 전형적인 패턴 함께 연습하기
    
    <aside>
    💡 튜터 님의 설명을 통해 이해해보겠습니다.
    이번 시간에는 따라치기보다 원리를 이해하는데 집중해보세요!
    
    </aside>
    
    - (1) 미세먼지(IDEX_MVL)의 값이 40 미만인 구 이름(MSRSTE_NM)과 값을 출력하기
        - **[코드스니펫] 서울시 미세먼지 값**
            
            ```jsx
            let mise_list = [
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "도심권",
                MSRSTE_NM: "중구",
                PM10: 22,
                PM25: 14,
                O3: 0.018,
                NO2: 0.015,
                CO: 0.4,
                SO2: 0.002,
                IDEX_NM: "좋음",
                IDEX_MVL: 31,
                ARPLT_MAIN: "O3",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "도심권",
                MSRSTE_NM: "종로구",
                PM10: 24,
                PM25: 18,
                O3: 0.013,
                NO2: 0.016,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 39,
                ARPLT_MAIN: "PM25",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "도심권",
                MSRSTE_NM: "용산구",
                PM10: 0,
                PM25: 15,
                O3: 0.012,
                NO2: 0.027,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "점검중",
                IDEX_MVL: -99,
                ARPLT_MAIN: "점검중",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서북권",
                MSRSTE_NM: "은평구",
                PM10: 36,
                PM25: 14,
                O3: 0.019,
                NO2: 0.018,
                CO: 0.5,
                SO2: 0.005,
                IDEX_NM: "좋음",
                IDEX_MVL: 42,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서북권",
                MSRSTE_NM: "서대문구",
                PM10: 28,
                PM25: 9,
                O3: 0.018,
                NO2: 0.015,
                CO: 0.6,
                SO2: 0.004,
                IDEX_NM: "좋음",
                IDEX_MVL: 37,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서북권",
                MSRSTE_NM: "마포구",
                PM10: 26,
                PM25: 8,
                O3: 0.012,
                NO2: 0.021,
                CO: 0.5,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 36,
                ARPLT_MAIN: "NO2",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동북권",
                MSRSTE_NM: "광진구",
                PM10: 17,
                PM25: 9,
                O3: 0.018,
                NO2: 0.016,
                CO: 0.6,
                SO2: 0.001,
                IDEX_NM: "좋음",
                IDEX_MVL: 31,
                ARPLT_MAIN: "O3",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동북권",
                MSRSTE_NM: "성동구",
                PM10: 21,
                PM25: 12,
                O3: 0.018,
                NO2: 0.017,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 33,
                ARPLT_MAIN: "PM25",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동북권",
                MSRSTE_NM: "중랑구",
                PM10: 27,
                PM25: 10,
                O3: 0.015,
                NO2: 0.019,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 34,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동북권",
                MSRSTE_NM: "동대문구",
                PM10: 26,
                PM25: 9,
                O3: 0.016,
                NO2: 0.017,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 34,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동북권",
                MSRSTE_NM: "성북구",
                PM10: 27,
                PM25: 8,
                O3: 0.022,
                NO2: 0.014,
                CO: 0.5,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 37,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동북권",
                MSRSTE_NM: "도봉구",
                PM10: 25,
                PM25: 12,
                O3: 0.024,
                NO2: 0.011,
                CO: 0.3,
                SO2: 0.002,
                IDEX_NM: "좋음",
                IDEX_MVL: 41,
                ARPLT_MAIN: "O3",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동북권",
                MSRSTE_NM: "강북구",
                PM10: 30,
                PM25: 15,
                O3: 0.022,
                NO2: 0.02,
                CO: 0.4,
                SO2: 0.002,
                IDEX_NM: "좋음",
                IDEX_MVL: 39,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동북권",
                MSRSTE_NM: "노원구",
                PM10: 21,
                PM25: 14,
                O3: 0.017,
                NO2: 0.016,
                CO: 0.4,
                SO2: 0.004,
                IDEX_NM: "좋음",
                IDEX_MVL: 36,
                ARPLT_MAIN: "PM25",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서남권",
                MSRSTE_NM: "강서구",
                PM10: 36,
                PM25: 16,
                O3: 0.021,
                NO2: 0.013,
                CO: 0.4,
                SO2: 0.004,
                IDEX_NM: "좋음",
                IDEX_MVL: 42,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서남권",
                MSRSTE_NM: "구로구",
                PM10: 23,
                PM25: 10,
                O3: 0.022,
                NO2: 0.016,
                CO: 0.3,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 37,
                ARPLT_MAIN: "O3",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서남권",
                MSRSTE_NM: "영등포구",
                PM10: 29,
                PM25: 15,
                O3: 0.01,
                NO2: 0.022,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 41,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서남권",
                MSRSTE_NM: "동작구",
                PM10: 29,
                PM25: 15,
                O3: 0.012,
                NO2: 0.023,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 41,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서남권",
                MSRSTE_NM: "관악구",
                PM10: 27,
                PM25: 12,
                O3: 0.012,
                NO2: 0.022,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 37,
                ARPLT_MAIN: "NO2",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서남권",
                MSRSTE_NM: "금천구",
                PM10: 25,
                PM25: 15,
                O3: 0.015,
                NO2: 0.02,
                CO: 0.4,
                SO2: 0.004,
                IDEX_NM: "좋음",
                IDEX_MVL: 43,
                ARPLT_MAIN: "PM25",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "서남권",
                MSRSTE_NM: "양천구",
                PM10: 0,
                PM25: 14,
                O3: 0.016,
                NO2: 0.017,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "점검중",
                IDEX_MVL: -99,
                ARPLT_MAIN: "점검중",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동남권",
                MSRSTE_NM: "강남구",
                PM10: 31,
                PM25: 16,
                O3: 0.018,
                NO2: 0.018,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 39,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동남권",
                MSRSTE_NM: "서초구",
                PM10: 34,
                PM25: 13,
                O3: 0.024,
                NO2: 0.019,
                CO: 0.3,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 41,
                ARPLT_MAIN: "PM10",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동남권",
                MSRSTE_NM: "송파구",
                PM10: 25,
                PM25: 6,
                O3: 0.014,
                NO2: 0.025,
                CO: 0.4,
                SO2: 0.003,
                IDEX_NM: "좋음",
                IDEX_MVL: 42,
                ARPLT_MAIN: "NO2",
              },
              {
                MSRDT: "201912052100",
                MSRRGN_NM: "동남권",
                MSRSTE_NM: "강동구",
                PM10: 24,
                PM25: 14,
                O3: 0.016,
                NO2: 0.02,
                CO: 0.4,
                SO2: 0.002,
                IDEX_NM: "좋음",
                IDEX_MVL: 39,
                ARPLT_MAIN: "PM25",
              },
            ];
            ```
            
        
        ```jsx
        for (let i = 0; i < mise_list.length; i++) {
          let mise = mise_list[i];
          if (mise["IDEX_MVL"] < 40) {
            let gu_name = mise["MSRSTE_NM"];
            let gu_mise = mise["IDEX_MVL"];
            console.log("40보다 작은 구: " + gu_name + ", " + gu_mise);
          }
        }
        ```
        
        40 이하든, 35 이하든 유용하게 쓸 수 있게, 함수로 만들어볼까요?
        
        ```jsx
        function show_gus(index) {
          for (let i = 0; i < mise_list.length; i++) {
            let mise = mise_list[i];
            if (mise["IDEX_MVL"] < index) {
              let gu_name = mise["MSRSTE_NM"];
              let gu_mise = mise["IDEX_MVL"];
        	    console.log(gu_name, gu_mise);
            }
          }
        }
        
        // 이러면 아래와 같은 것이 가능!
        show_gus(40) // 40보다 작은 구만 출력!
        show_gus(35) // 35보다 작은 구만 출력!
        ```
        
- 2) 앗, 문법이 어렵다고요?
    
    
    - 다음 시간에 연습 예제들도 준비해뒀어요. (😎워밍업!)
    
    - 기억하시나요? 문법을 외우는 것은 중요하지 않아요. 예를 들어 if문을 어떻게 썼더라- 하는 것은 괜찮습니다. 코드는 복사해서 쓰세요. 얼개를 이해하는 게 중요합니다!

## 20**. 1주차 끝 & 숙제 설명**

<aside>
📃 아래 예시화면을 보고, 부트스트랩 또는 템플릿을 활용해서 팬명록의 메인 페이지를 완성해주세요. (내가 좋아하는 아티스트로 해보세요!)

</aside>

- **[코드스니펫] 부트스트랩 시작 템플릿**
    
    ```html
    <!doctype html>
    <html lang="en">
    
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
            integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
            integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
            crossorigin="anonymous"></script>
    
        <title>스파르타코딩클럽 | 부트스트랩 연습하기</title>
    </head>
    
    <body>
        <h1>이걸로 시작해보죠!</h1>
    </body>
    
    </html>
    ```
    
- **[코드스니펫] 부트스트랩 컴포넌트 5.0**
    
    ```html
    https://getbootstrap.com/docs/5.0/components/buttons/
    ```
    
- 예시 화면
    
    <aside>
    👻 **힌트!** 부트스트랩의 Card → Quote 를 이용하기! + 폰트도 잊지 마세요! [(구글폰트 링크)](https://fonts.google.com/?subset=korean)
    
    </aside>
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a3af1f9a-8622-4d97-bf18-d5eaa8261f2a/Untitled.png)
    

## HW. 1주차 숙제 해설

- **[코드스니펫] 1주차 숙제 답안 코드**
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
            integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
            integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
            crossorigin="anonymous"></script>
    
        <title>초미니홈피 - 팬명록</title>
    
        <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR:wght@200;300;400;500;600;700;900&display=swap" rel="stylesheet">
        <style>
            * {
                font-family: 'Noto Serif KR', serif;
            }
            .mypic {
                width: 100%;
                height: 300px;
    
                background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://cdn.topstarnews.net/news/photo/201807/456143_108614_510.jpg');
                background-position: center 30%;
                background-size: cover;
    
                color: white;
    
                display: flex;
                flex-direction: column;
                align-items: center;
                justify-content: center;
            }
    
            .mypost {
                width: 95%;
                max-width: 500px;
                margin: 20px auto 20px auto;
    
                box-shadow: 0px 0px 3px 0px black;
                padding: 20px;
            }
    
            .mypost > button {
                margin-top: 15px;
            }
    
            .mycards {
                width: 95%;
                max-width: 500px;
                margin: auto;
            }
    
            .mycards > .card {
                margin-top: 10px;
                margin-bottom: 10px;
            }
        </style>
    </head>
    <body>
        <div class="mypic">
            <h1>십센치(10cm) 팬명록</h1>
        </div>
        <div class="mypost">
            <div class="form-floating mb-3">
                <input type="text" class="form-control" id="name" placeholder="url">
                <label for="floatingInput">닉네임</label>
            </div>
            <div class="form-floating">
                <textarea class="form-control" placeholder="Leave a comment here" id="comment"
                    style="height: 100px"></textarea>
                <label for="floatingTextarea2">응원댓글</label>
            </div>
            <button onclick="save_comment()" type="button" class="btn btn-dark">응원 남기기</button>
        </div>
        <div class="mycards" id="comment-list">
            <div class="card">
                <div class="card-body">
                    <blockquote class="blockquote mb-0">
                        <p>새로운 앨범 너무 멋져요!</p>
                        <footer class="blockquote-footer">호빵맨</footer>
                    </blockquote>
                </div>
            </div>
            <div class="card">
                <div class="card-body">
                    <blockquote class="blockquote mb-0">
                        <p>새로운 앨범 너무 멋져요!</p>
                        <footer class="blockquote-footer">호빵맨</footer>
                    </blockquote>
                </div>
            </div>
            <div class="card">
                <div class="card-body">
                    <blockquote class="blockquote mb-0">
                        <p>새로운 앨범 너무 멋져요!</p>
                        <footer class="blockquote-footer">호빵맨</footer>
                    </blockquote>
                </div>
            </div>
        </div>
    </body>
    </html>
    ```
