---
layout: post
title: 스파르타코딩클럽 웹개발 종합반
subtitle: 1주차 - 1
tags: [HTML, CSS]
comments: true
---
<aside>

## ** HTML, CSS 기본 내용**

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
        - **HTML기초**
            
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
        👉 **자동정렬**
         **ctrl+alt+L**
        
        </aside>
        ## **04. Quiz_간단한 로그인 페이지 만들어보기**

- 1) ✍간단한 로그인 페이지 만들기
            
        
    - A. 함께하기(완성본)
        
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
            
        - **로그인HTML**
            
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

