---
layout: post
title: 스파르타코딩클럽 웹개발 종합반 - 2주차
subtitle: 2-1
tags: [jQuery, Ajax]
comments: true
---

## **jQuery, Ajax**

- 1) 오늘 배울 것 이야기 - 2주차: jQuery, Ajax
    
    <aside>
    👉 jQuery를 이용해 Javascript로 HTML을 쉽게 제어하고, Ajax를 이용해 다시 서버에 데이터를 요청하고 받아보기.
    

    
    </aside>
    
    ![Untitle](https://teamsparta.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F6434b1c6-1baf-4746-a253-19cd70fd5825%2FUntitled.png?table=block&id=f0b78f46-9992-47cc-af22-bf783b3cbdee&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=1970&userId=&cache=v2)
    
- 2) Javascript 잠깐 복습 - 홀짝 판별 onclick 함수 만들어보기
    - 짝/홀수 판단하는 방법
        
        ```jsx
        let even = 4;
        console.log(even % 2); // 2로 나눈 나머지가 0입니다.
        let odd = 5;
        console.log(odd % 2); // 2로 나눈 나머지가 1입니다.
        ```
        
    - **짝/홀수 onclick 함수(완성)**
        
        ```jsx
            <script>
                let count = 1;
                function hey() {
                    if (count % 2 == 0) {
                        alert('짝짝짝👏');
                    } else {
                        alert('홀홀홀🎅');
                    }
        						count += 1;
                }
            </script>
        ```

## **JQuery 시작하기**

- 1) jQuery 란?
    - HTML의 요소들을 조작하는, 편리한 Javascript를 미리 작성해둔 것. 라이브러리!
        
        <aside>
        👉 Javascript로도 모든 기능(예 - 버튼 글씨 바꾸기 등)을 구현할 수는 있지만,
        
        1) 코드가 복잡하고, 2) 브라우저 간 호환성 문제도 고려해야해서,
        **j**Query라는 라이브러리가 등장했다.
        
        </aside>
        
    - jQuery와 Javascript - 코드 비교해보기
        
        <aside>
        👉 jQuery는 Javascript와 다른 특별한 소프트웨어가 아니라 미리 작성된 Javascript 코드.(가져다 쓰는것이기 때문에, 쓰기 전에 "import" 필수!)
        
        </aside>
        
        Javascript로 길고 복잡하게 써야 하는 것을
        
        ```jsx
        document.getElementById("element").style.display = "none";
        ```
        
        jQuery로 보다 직관적으로 쓸 수 있다.
        
        ```jsx
        $('#element').hide();
        ```
        
- 2) jQuery 사용하기
    - 미리 작성된 Javascript 코드를 가져오는 것을 'import'라고 한다.
        
        <aside>
        👉 jQuery CDN 부분을 참고해서 임포트하기: [(링크)](https://www.w3schools.com/jquery/jquery_get_started.asp)
        
        </aside>
        
        - **jQuery CDN**
            
            ```html
            https://www.w3schools.com/jquery/jquery_get_started.asp
            ```
            
    - <.head> 와 <./head> 사이에 아래를 넣으면 끝!
        
        
        ```html
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
        ```
        
    - jQuery를 사용하는 방법
        
        <aside>
        👉 css와 마찬가지로, jQuery를 쓸 때에도 "가리켜야" → 조작할 수 있다.
        예) 특정 인풋박스의 값을 → 가져와줘!
        예) 특정 div를 → 안보이게 해줘!
        
        css에서는 선택자로 class를 쓰고,
        jQuery에서는 id 값을 통해 특정 버튼/인풋박스/div/.. 등을 가리키게 됩니다.
        
        
        </aside>
        

## **JQuery 다뤄보기 (1)**

- 자주쓰는 jQuery들 다뤄보기  
        
    - **[코드스니펫] 1주차 완성본**
        
        ```jsx
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
            <script>
                function hey(){
                    alert('안녕!');
                }
            </script>
        </head>
        
        <body>
        <div class="mytitle">
            <h1>내 생애 최고의 영화들</h1>
            <button onclick="hey()">영화 기록하기</button>
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
        
    - 1. input 박스의 값을 가져와보기
        
        ```jsx
        <div class="form-floating mb-3">
            <input id="url" type="email" class="form-control" placeholder="name@example.com">
            <label>영화URL</label>
        </div>
        ```
        
        ```jsx
        // 크롬 개발자도구 콘솔창에서 쳐보기
        // id 값이 url인 곳을 가리키고, val()로 값을 가져온다.
        $('#url').val();
        
        // 입력할때는?
        $('#url').val('이렇게 하면 입력이 가능하지만!');
        ```
        
    - 2. div 보이기 / 숨기기
        
        ```jsx
        <div class="mypost" id="post-box">
            <div class="form-floating mb-3">
                <input id="url" type="email" class="form-control" placeholder="name@example.com">
                <label>영화URL</label>
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
        ```
        
        ```jsx
        // 크롬 개발자도구 콘솔창에 쳐보기
        // id 값이 post-box인 곳을 가리키고, hide()로 안보이게 한다.
        $('#post-box').hide();
        
        // show()로 보이게 한다.
        $('#post-box').show();
        ```
        

## **04. JQuery 다뤄보기 (2)**

- 3. 태그 내 html 입력하기
    - <div> ~ </div> 내에,
    동적으로 html을 넣고 싶을 땐? (예를 들어, 포스팅되면 → 카드 추가)
    - 카드가 붙는 div 에 id를 추가해주는 것이 핵심!
    
    ```jsx
    <div class="mycards">
        <div class="row row-cols-1 row-cols-md-4 g-4" id="cards-box">
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
    ```
    
    1) 버튼을 넣어보기
    
    ```jsx
    let temp_html = `<button>나는 추가될 버튼이다!</button>`;
    $('#cards-box').append(temp_html);
    ```
    
    2) 버튼 말고, 카드를 넣어보기
    
    ```jsx
    // 주의: 홑따옴표(')가 아닌 backtick(`)으로 감싸야 합니다.
    // 숫자 1번 키 왼쪽의 버튼을 누르면 backtick(`)이 입력됩니다.
    // backtick을 사용하면 문자 중간에 Javascript 변수를 삽입할 수 있습니다.
    let title = '영화 제목이 들어갑니다';
    
    let temp_html = `<div class="col">
    				            <div class="card h-100">
    				                <img src="https://movie-phinf.pstatic.net/20210728_221/1627440327667GyoYj_JPEG/movie_image.jpg"
    				                     class="card-img-top" alt="...">
    				                <div class="card-body">
    				                    <h5 class="card-title">${title}</h5>
    				                    <p class="card-text">여기에 영화에 대한 설명이 들어갑니다.</p>
    				                    <p>⭐⭐⭐</p>
    				                    <p class="mycomment">나의 한줄 평을 씁니다</p>
    				                </div>
    				            </div>
    				        </div>`;
    $('#cards-box').append(temp_html);
    ```
    

## **05. JQuery 적용하기(포스팅 박스)**

- 1) 포스팅박스 열기/닫기 기능을 붙여보기
    - **[코드스니펫] 스파르타피디아 URL**
        
        ```html
        http://spartacodingclub.shop/web/movie
        ```
        
    - (1) 완성된 모습 먼저 보기
        
        '영화 기록하기' 버튼을 누르면 숨겨진 창이 나타나고, '닫기'를 누르면 없어집니다.
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/57650491-3d1e-4566-9c26-3990cf5337da/Untitled.png)
        
    - (2) 포스팅 박스 열기 버튼에 function을 달기
        
        ```jsx
        function open_box(){
            alert('열린다!')
        }
        function close_box(){
            alert('닫힌다!')
        }
        
        <button onclick="open_box()">영화 기록하기</button>
        
        <button onclick="close_box()" type="button" class="btn btn-outline-dark">닫기</button>
        ```
        
    - (3) 클릭 해서 포스팅 박스를 여닫게 하기
        - 포스팅 박스에 id 값을 주기 (이미 가지고 있음!)
            
            ```jsx
            <div class="mypost" id="post-box">
                <div class="form-floating mb-3">
                    <input id="url" type="email" class="form-control" placeholder="name@example.com">
                    <label>영화URL</label>
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
                    <textarea id="comment" class="form-control" placeholder="Leave a comment here" id="floatingTextarea2"
                              style="height: 100px"></textarea>
                    <label for="floatingTextarea2">코멘트</label>
                </div>
                <div class="mybtns">
                    <button type="button" class="btn btn-dark">기록하기</button>
                    <button onclick="close_box()" type="button" class="btn btn-outline-dark">닫기</button>
                </div>
            </div>
            ```
            
        - 포스팅 박스 제어하기
            
            ```jsx
            function open_box(){
                $('#post-box').show()
            }
            function close_box(){
                $('#post-box').hide()
            }
            ```
            
        - post-box를 시작부터 감춰두기 (css의 display:none 속성!)
            
            ```css
            .mypost {
                width: 95%;
                max-width: 500px;
                margin: 20px auto 0px auto;
                padding: 20px;
                box-shadow: 0px 0px 3px 0px gray;
                
                display: none;
            }
            ```
            
    - (4) 완성코드
        - **[코드스니펫] 포스팅박스(완성)**
            
            ```jsx
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
            
                        display: none;
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
                <script>
                    function open_box(){
                        $('#post-box').show()
                    }
                    function close_box(){
                        $('#post-box').hide()
                    }
                </script>
            </head>
            
            <body>
            <div class="mytitle">
                <h1>내 생애 최고의 영화들</h1>
                <button onclick="open_box()">영화 기록하기</button>
            </div>
            <div class="mypost" id="post-box">
                <div class="form-floating mb-3">
                    <input id="url" type="email" class="form-control" placeholder="name@example.com">
                    <label>영화URL</label>
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
                    <textarea id="comment" class="form-control" placeholder="Leave a comment here" id="floatingTextarea2"
                              style="height: 100px"></textarea>
                    <label for="floatingTextarea2">코멘트</label>
                </div>
                <div class="mybtns">
                    <button type="button" class="btn btn-dark">기록하기</button>
                    <button onclick="close_box()" type="button" class="btn btn-outline-dark">닫기</button>
                </div>
            </div>
            <div class="mycards">
                <div class="row row-cols-1 row-cols-md-4 g-4" id="cards-box">
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
            

## **06. Quiz_JQuery 연습하기 (1)**

- ✍두 개를 같이 연습해야 빨리 늘어요!
    
    <aside>
    👉 30분 정도 각자 해보고, 튜터와 함께 풀이해봅시다!
    (퀴즈 코드의 빈 칸을 채워서, 완성본으로 만들기!)
    
    </aside>
    
    - **[코드스니펫] 퀴즈 완성본보기**
        
        ```css
        http://spartacodingclub.shop/ajaxquiz/00_0
        ```
        
    - Q. 퀴즈 코드
        
        <aside>
        👉 파일을 하나 만들고 아래 코드를 붙여넣어 주세요.
        
        </aside>
        
        - **[코드스니펫] Jquery 퀴즈**
            
            ```jsx
            <!doctype html>
            <html lang="ko">
            
            <head>
                <meta charset="UTF-8">
                <title>jQuery 연습하고 가기!</title>
            
                <!-- JQuery를 import 합니다 -->
                <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
            
                <style type="text/css">
                    div.question-box {
                        margin: 10px 0 20px 0;
                    }
                </style>
            
                <script>
                    function q1() {
                        // 1. input-q1의 입력값을 가져온다. $('# .... ').val() 이렇게!
                        // 2. 만약 입력값이 빈칸이면 if(입력값=='')
                        // 3. alert('입력하세요!') 띄우기
                        // 4. alert(입력값) 띄우기
                    }
            
                    function q2() {
                        // 1. input-q2 값을 가져온다.
                        // 2. 만약 가져온 값에 @가 있으면 (includes 이용하기 - 구글링!)
                        // 3. info@gmail.com -> gmail 만 추출해서 ( .split('@') 을 이용하자!)
                        // 4. alert(도메인 값);으로 띄우기
                        // 5. 만약 이메일이 아니면 '이메일이 아닙니다.' 라는 얼럿 띄우기
                    }
            
                    function q3() {
                        // 1. input-q3 값을 가져온다. let txt = ... q1, q2에서 했던 걸 참고!
                        // 2. 가져온 값을 이용해 names-q3에 붙일 태그를 만든다. (let temp_html = `<li>${txt}</li>`) 요렇게!
                        // 3. 만들어둔 temp_html을 names-q3에 붙인다.(jQuery의 $('...').append(temp_html)을 이용하면 굿!)
                    }
            
                    function q3_remove() {
                        // 1. names-q3의 내부 태그를 모두 비운다.(jQuery의 $('....').empty()를 이용하면 굿!)
                    }
            
                </script>
            
            </head>
            
            <body>
                <h1>jQuery + Javascript의 조합을 연습하자!</h1>
            
                <div class="question-box">
                    <h2>1. 빈칸 체크 함수 만들기</h2>
                    <h5>1-1. 버튼을 눌렀을 때 입력한 글자로 얼럿 띄우기</h5>
                    <h5>[완성본]1-2. 버튼을 눌렀을 때 칸에 아무것도 없으면 "입력하세요!" 얼럿 띄우기</h5>
                    <input id="input-q1" type="text" /> <button onclick="q1()">클릭</button>
                </div>
                <hr />
                <div class="question-box">
                    <h2>2. 이메일 판별 함수 만들기</h2>
                    <h5>2-1. 버튼을 눌렀을 때 입력받은 이메일로 얼럿 띄우기</h5>
                    <h5>2-2. 이메일이 아니면(@가 없으면) '이메일이 아닙니다'라는 얼럿 띄우기</h5>
                    <h5>[완성본]2-3. 이메일 도메인만 얼럿 띄우기</h5>
                    <input id="input-q2" type="text" /> <button onclick="q2()">클릭</button>
                </div>
                <hr />
                <div class="question-box">
                    <h2>3. HTML 붙이기/지우기 연습</h2>
                    <h5>3-1. 이름을 입력하면 아래 나오게 하기</h5>
                    <h5>[완성본]3-2. 다지우기 버튼을 만들기</h5>
                    <input id="input-q3" type="text" placeholder="여기에 이름을 입력" />
                    <button onclick="q3()">이름 붙이기</button>
                    <button onclick="q3_remove()">다지우기</button>
                    <ul id="names-q3">
                        <li>세종대왕</li>
                        <li>임꺽정</li>
                    </ul>
                </div>
            </body>
            
            </html>
            ```
            

## **07. Quiz_JQuery 연습하기 (2)**

- A. 같이 풀어보기
    - **[코드스니펫] Jquery 퀴즈(완성)**
        
        ```jsx
        <!doctype html>
        <html lang="ko">
        
        <head>
            <meta charset="UTF-8">
            <title>jQuery 연습하고 가기!</title>
        
            <!-- JQuery를 import 합니다 -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
        
            <style type="text/css">
                div.question-box {
                    margin: 10px 0 20px 0;
                }
            </style>
        
            <script>
                function q1() {
                    // 1. input-q1의 입력값을 가져온다.
                    let value = $('#input-q1').val();
                    // 2. 만약 입력값이 빈칸이면 if(입력값=='')
                    if (value == '') {
                        // 3. alert('입력하세요!') 띄우기
                        alert('입력하세요!');
                    } else {
                        // 4. alert(입력값) 띄우기
                        alert(value);
                    }
                }
        
                function q2() {
                    // 1. input-q2 값을 가져온다.
                    let email = $('#input-q2').val();
                    // 2. 만약 가져온 값에 @가 있으면 (includes 이용하기 - 찾아보자!)
                    if (email.includes('@')) {
                        // 3. info@gmail.com -> gmail 만 추출해서
                        // 4. alert(도메인 값);으로 띄우기
                        let domainWithDot = email.split('@')[1];
                        let onlyDomain = domainWithDot.split('.')[0];
                        alert(onlyDomain);
                    } else {
                        // 5. 만약 이메일이 아니면 '이메일이 아닙니다.' 라는 얼럿 띄우기
                        alert('이메일이 아닙니다.');
                    }
                }
        
                function q3() {
                    // 1. input-q3 값을 가져온다.
                    let newName = $('#input-q3').val();
                    if (newName == '') {
                        alert('이름을 입력하세요');
                        return;
                    }
                    // 2. 가져온 값을 이용해 names-q3에 붙일 태그를 만든다. (let temp_html = `<li>${가져온 값}</li>`)
                    let temp_html = `<li>${newName}</li>`;
                    // 3. 만들어둔 temp_html을 names-q3에 붙인다.(jQuery의 $('...').append(temp_html)을 이용하면 굿!)
                    $('#names-q3').append(temp_html);
                }
        
                function q3_remove() {
                    // 1. names-q3의 내부 태그를 모두 비운다.(jQuery의 $('....').empty()를 이용하면 굿!)
                    $('#names-q3').empty();
                }
        
            </script>
        
        </head>
        
        <body>
            <h1>jQuery + Javascript의 조합을 연습하자!</h1>
        
            <div class="question-box">
                <h2>1. 빈칸 체크 함수 만들기</h2>
                <h5>1-1. 버튼을 눌렀을 때 입력한 글자로 얼럿 띄우기</h5>
                <h5>[완성본]1-2. 버튼을 눌렀을 때 칸에 아무것도 없으면 "입력하세요!" 얼럿 띄우기</h5>
                <input id="input-q1" type="text" /> <button onclick="q1()">클릭</button>
            </div>
            <hr />
            <div class="question-box">
                <h2>2. 이메일 판별 함수 만들기</h2>
                <h5>2-1. 버튼을 눌렀을 때 입력받은 이메일로 얼럿 띄우기</h5>
                <h5>2-2. 이메일이 아니면(@가 없으면) '이메일이 아닙니다'라는 얼럿 띄우기</h5>
                <h5>[완성본]2-3. 이메일 도메인만 얼럿 띄우기</h5>
                <input id="input-q2" type="text" /> <button onclick="q2()">클릭</button>
            </div>
            <hr />
            <div class="question-box">
                <h2>3. HTML 붙이기/지우기 연습</h2>
                <h5>3-1. 이름을 입력하면 아래 나오게 하기</h5>
                <h5>[완성본]3-2. 다지우기 버튼을 만들기</h5>
                <input id="input-q3" type="text" placeholder="여기에 이름을 입력" />
                <button onclick="q3()">이름 붙이기</button>
                <button onclick="q3_remove()">다지우기</button>
                <ul id="names-q3">
                    <li>세종대왕</li>
                    <li>임꺽정</li>
                </ul>
            </div>
        </body>
        
        </html>
        ```
        
    
