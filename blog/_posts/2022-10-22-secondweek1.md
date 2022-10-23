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
        
        예) 특정 인풋박스의 값을 → 가져와줘!
        예) 특정 div를 → 안보이게 해줘!
        
        css에서는 선택자로 class를 쓰고,
        jQuery에서는 id 값을 통해 특정 버튼/인풋박스/div/.. 등을 가리키게 된다.
        
        
        </aside>
        

## **JQuery 다뤄보기 (1)**

- 자주쓰는 jQuery들 다뤄보기  
        
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
        

## **JQuery 다뤄보기 (2)**

- 3. 태그 내 html 입력하기
    - <.div> ~ <./div> 내에,
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
    // 주의: 홑따옴표(')가 아닌 backtick(` / 숫자 1번 키) 사용.
    // backtick을 사용하면 문자 중간에 Javascript 변수를 삽입 가능.
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
    

## **JQuery 적용하기(포스팅 박스)**

- 1) 포스팅박스 열기/닫기 기능을 붙여보기
    - **스파르타피디아 URL**
        
        ```html
        http://spartacodingclub.shop/web/movie
        ```
        
    - (1) 미리보기
        
        '영화 기록하기' 버튼을 누르면 숨겨진 창이 나타나고, '닫기'를 누르면 없어진다.
        
        ![Untitled]([https://s3-us-west-2.amazonaws.com/secure.notion-static.com/57650491-3d1e-4566-9c26-3990cf5337da/Untitled.png](https://teamsparta.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F57650491-3d1e-4566-9c26-3990cf5337da%2FUntitled.png?table=block&id=3a7fbb2c-276c-43d9-a93b-9ed6b5ae5a4c&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=2000&userId=&cache=v2))
        
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
            
- 완성코드
        - **포스팅박스(완성)**
            
```JSX
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
            
