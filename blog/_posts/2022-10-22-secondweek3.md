---
layout: post
title: 스파르타코딩클럽 웹개발 종합반 - 2주차
subtitle: 2-3
tags: [Ajax, jQuery]
comments: true
---

## **09. Ajax 시작하기**

- 1) Ajax 시작하기
    - 크롬 개발자 도구에 다음과 같이 써보세요
        
        <aside>
        👉 참고! Ajax는 jQuery를 임포트한 페이지에서만 동작 가능합니다.
        
        즉, [http://google.com/](http://google.com/) 과 같은 화면에서 개발자도구를 열면, jQuery가 임포트 되어있지 않기 때문에 아래와 같은 에러가 뜹니다.
        
        *Uncaught TypeError: $.ajax is not a function*
        → ajax라는 게 없다는 뜻
        
        </aside>
        
        - **[코드스니펫] 미세먼지 OpenAPI**
            
            ```html
            http://spartacodingclub.shop/sparta_api/seoulair
            ```
            
        - **[코드스니펫] Ajax 기본 골격**
            
            ```jsx
            $.ajax({
              type: "GET",
              url: "여기에URL을입력",
              data: {},
              success: function(response){
                console.log(response)
              }
            })
            ```
            
        
        Ajax 코드 해설
        
        ```jsx
        $.ajax({
          type: "GET", // GET 방식으로 요청한다.
          url: "http://spartacodingclub.shop/sparta_api/seoulair",
          data: {}, // 요청하면서 함께 줄 데이터 (GET 요청시엔 비워두세요)
          success: function(response){ // 서버에서 준 결과를 response라는 변수에 담음
            console.log(response) // 서버에서 준 결과를 이용해서 나머지 코드를 작성
          }
        })
        ```
        
    - $ajax 코드 설명
        - type: "GET" → GET 방식으로 요청한다.
        - url: 요청할 url
        - data: 요청하면서 함께 줄 데이터 (GET 요청시엔 비워두세요)
            
            <aside>
            👉 리마인드
            GET 요청은, url뒤에 아래와 같이 붙여서 데이터를 가져갑니다.
            http://naver.com?param=value&param2=value2 
            
            POST 요청은, data : {} 에 넣어서 데이터를 가져갑니다.
            data: { param: 'value', param2: 'value2' },
            
            </aside>
            
        - success: 성공하면, response 값에 서버의 결과 값을 담아서 함수를 실행한다.
            
            <aside>
            👉 결과가 어떻게 response에 들어가나요? → 받아 들이셔야 합니다..!
            (대부분의 개발자들도 내부 원리는 코드를 안 뜯어봐서 몰라요.^^;;)
            
            </aside>
            
            ```jsx
            success: function(response){ // 서버에서 준 결과를 response라는 변수에 담음
              console.log(response) 
            }
            ```
            
- 2) Ajax 통신의 결과값을 이용해보기
    - 위에서 했던 Ajax 통신을 발전시켜볼게요!
        
        ```jsx
        $.ajax({
          type: "GET", // GET 방식으로 요청한다.
          url: "http://spartacodingclub.shop/sparta_api/seoulair",
          data: {}, // 요청하면서 함께 줄 데이터 (GET 요청시엔 비워두세요)
          success: function(response){ // 서버에서 준 결과를 response라는 변수에 담음
            console.log(response) // 서버에서 준 결과를 이용해서 나머지 코드를 작성
          }
        })
        ```
        
    - 개발자도구 콘솔에 찍어보기
        
        ```jsx
        $.ajax({
          type: "GET",
          url: "http://spartacodingclub.shop/sparta_api/seoulair",
          data: {},
          success: function(response){
        		// 값 중 도봉구의 미세먼지 값만 가져와보기
        		let dobong = response["RealtimeCityAir"]["row"][11];
        		let gu_name = dobong['MSRSTE_NM'];
        		let gu_mise = dobong['IDEX_MVL'];
        		console.log(gu_name, gu_mise);
          }
        })
        ```
        
    - 모든 구의 미세먼지 값을 찍어보기
        
        ```jsx
        $.ajax({
          type: "GET",
          url: "http://spartacodingclub.shop/sparta_api/seoulair",
          data: {},
          success: function (response) {
            let mise_list = response["RealtimeCityAir"]["row"];
            for (let i = 0; i < mise_list.length; i++) {
              let mise = mise_list[i];
              let gu_name = mise["MSRSTE_NM"];
              let gu_mise = mise["IDEX_MVL"];
              console.log(gu_name, gu_mise);
            }
          }
        });
        ```
        
        - 복습할 때 참고! - 해설) 모든 구의 미세먼지 값을 찍어보기
            1. 미세먼지 데이터가 어디에 있는지 찾기
                
                ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cf6e770d-9618-4c1d-beef-afb23b3cd2c9/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cf6e770d-9618-4c1d-beef-afb23b3cd2c9/Untitled.png)
                
                위 그림과 같이 RealtimeCityAir > row 에 미세먼지 데이터가 들어있습니다. 이걸 꺼내볼까요?
                
                ```jsx
                $.ajax({
                  type: "GET",
                  url: "http://spartacodingclub.shop/sparta_api/seoulair",
                  data: {},
                  success: function(response){
                		let mise_list = response["RealtimeCityAir"]["row"]; // 꺼내는 부분!
                		console.log(mise_list);
                  }
                })
                ```
                
            2. 반복문으로 구 데이터를 출력해보기
                
                ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/dc6ab951-95aa-4415-8977-fc988e04e3cc/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/dc6ab951-95aa-4415-8977-fc988e04e3cc/Untitled.png)
                
                row의 값을 mise_list에 담았으니, 반복문을 이용해보겠습니다!
                
                ```jsx
                $.ajax({
                  type: "GET",
                  url: "http://spartacodingclub.shop/sparta_api/seoulair",
                  data: {},
                  success: function (response) {
                    let mise_list = response["RealtimeCityAir"]["row"];
                    for (let i = 0; i < mise_list.length; i++) {
                      let mise = mise_list[i];
                      console.log(mise);
                    }
                  },
                });
                ```
                
            3. 구 데이터에서 구 이름, 미세먼지 수치를 골라내어 출력하기
                
                ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/41a0dbc3-2ad1-458f-baeb-08961f950b25/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/41a0dbc3-2ad1-458f-baeb-08961f950b25/Untitled.png)
                
                구 이름 키 값인 "MSRSTE_NM", 미세먼지 수치 키값인 "IDEX_MVL"의 밸류를 출력
                
                ```jsx
                $.ajax({
                  type: "GET",
                  url: "http://spartacodingclub.shop/sparta_api/seoulair",
                  data: {},
                  success: function (response) {
                    let mise_list = response["RealtimeCityAir"]["row"];
                    for (let i = 0; i < mise_list.length; i++) {
                      let mise = mise_list[i];
                      let gu_name = mise["MSRSTE_NM"];
                      let gu_mise = mise["IDEX_MVL"];
                      console.log(gu_name, gu_mise);
                    }
                  }
                });
                ```
                

## 10**. Ajax 함께 연습하기**

- 1) 서울시 OpenAPI(실시간 미세먼지 상태)를 이용하기
    - **[코드스니펫] Ajax 기본 골격**
        
        ```jsx
        $.ajax({
          type: "GET",
          url: "여기에URL을입력",
          data: {},
          success: function(response){
            console.log(response)
          }
        })
        ```
        
    - **[코드스니펫] 미세먼지 OpenAPI**
        
        ```html
        http://spartacodingclub.shop/sparta_api/seoulair
        ```
        
    - **[코드스니펫] Ajax 연습**
        
        ```jsx
        <!doctype html>
        <html lang="ko">
        
        <head>
            <meta charset="UTF-8">
            <title>jQuery 연습하고 가기!</title>
        
            <!-- jQuery를 import 합니다 -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
        
            <style type="text/css">
                div.question-box {
                    margin: 10px 0 20px 0;
                }
            </style>
        
            <script>
                function q1() {
                    // 여기에 코드를 입력하세요
                }
            </script>
        
        </head>
        
        <body>
            <h1>jQuery+Ajax의 조합을 연습하자!</h1>
        
            <hr />
        
            <div class="question-box">
                <h2>1. 서울시 OpenAPI(실시간 미세먼지 상태)를 이용하기</h2>
                <p>모든 구의 미세먼지를 표기해주세요</p>
                <p>업데이트 버튼을 누를 때마다 지웠다 새로 씌여져야 합니다.</p>
                <button onclick="q1()">업데이트</button>
                <ul id="names-q1">
                    <li>중구 : 82</li>
                    <li>종로구 : 87</li>
                    <li>용산구 : 84</li>
                    <li>은평구 : 82</li>
                </ul>
            </div>
        </body>
        
        </html>
        ```
        
    - **[코드스니펫] Ajax 연습(보기)**
        
        ```python
        http://spartacodingclub.shop/ajaxquiz/01
        ```
        
    - **[코드스니펫] Ajax 연습(완성)**
        
        ```jsx
        <!doctype html>
        <html lang="ko">
        
        <head>
            <meta charset="UTF-8">
            <title>jQuery 연습하고 가기!</title>
        
            <!-- jQuery를 import 합니다 -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
        
            <style type="text/css">
                div.question-box {
                    margin: 10px 0 20px 0;
                }
            </style>
        
            <script>
                function q1() {
                    // 여기에 코드를 입력하세요
                    $('#names-q1').empty();
                    $.ajax({
                        type: "GET",
                        url: "http://spartacodingclub.shop/sparta_api/seoulair",
                        data: {},
                        success: function (response) {
                            let rows = response["RealtimeCityAir"]["row"];
                            for (let i = 0; i < rows.length; i++) {
                                let gu_name = rows[i]['MSRSTE_NM'];
                                let gu_mise = rows[i]['IDEX_MVL'];
                                let temp_html = `<li>${gu_name} : ${gu_mise}</li>`
                                $('#names-q1').append(temp_html);
                            }
                        }
                    })
                }
            </script>
        
        </head>
        
        <body>
            <h1>jQuery+Ajax의 조합을 연습하자!</h1>
        
            <hr />
        
            <div class="question-box">
                <h2>1. 서울시 OpenAPI(실시간 미세먼지 상태)를 이용하기</h2>
                <p>모든 구의 미세먼지를 표기해주세요</p>
                <p>업데이트 버튼을 누를 때마다 지웠다 새로 씌여져야 합니다.</p>
                <button onclick="q1()">업데이트</button>
                <ul id="names-q1">
                </ul>
            </div>
        </body>
        
        </html>
        ```
        
    
    <aside>
    👉 [한걸음 더]
    미세먼지 수치가 70이상인 곳은 빨갛게 보여줄까요?
    
    </aside>
    
    - **[코드스니펫] Ajax 연습(완성-한걸음더)**
        
        ```jsx
        <!doctype html>
        <html lang="ko">
        
        <head>
            <meta charset="UTF-8">
            <title>jQuery 연습하고 가기!</title>
        
            <!-- jQuery를 import 합니다 -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
        
            <style type="text/css">
                div.question-box {
                    margin: 10px 0 20px 0;
                }
                .bad {
                    color: red;
                    font-weight: bold;
                }
            </style>
        
            <script>
                function q1() {
                    // 여기에 코드를 입력하세요
                    $('#names-q1').empty();
                    $.ajax({
                        type: "GET",
                        url: "http://spartacodingclub.shop/sparta_api/seoulair",
                        data: {},
                        success: function (response) {
                            let rows = response["RealtimeCityAir"]["row"];
                            for (let i = 0; i < rows.length; i++) {
                                let gu_name = rows[i]['MSRSTE_NM'];
                                let gu_mise = rows[i]['IDEX_MVL'];
        
                                let temp_html = ''
        
                                if (gu_mise > 70) {
                                    temp_html = `<li class="bad">${gu_name} : ${gu_mise}</li>`
                                } else {
                                    temp_html = `<li>${gu_name} : ${gu_mise}</li>`
                                }
                                
                                $('#names-q1').append(temp_html);
                            }
                        }
                    })
                }
            </script>
        
        </head>
        
        <body>
            <h1>jQuery+Ajax의 조합을 연습하자!</h1>
        
            <hr />
        
            <div class="question-box">
                <h2>1. 서울시 OpenAPI(실시간 미세먼지 상태)를 이용하기</h2>
                <p>모든 구의 미세먼지를 표기해주세요</p>
                <p>업데이트 버튼을 누를 때마다 지웠다 새로 씌여져야 합니다.</p>
                <button onclick="q1()">업데이트</button>
                <ul id="names-q1">
                </ul>
            </div>
        </body>
        
        </html>
        ```
        

 

## 11**. Quiz_Ajax 연습하기(1)**

- 1) ✍서울시 OpenAPI(실시간 따릉이 현황)을 이용하기
    - **[코드스니펫] 따릉이 OpenAPI**
        
        ```html
        http://spartacodingclub.shop/sparta_api/seoulbike
        ```
        
    - **[코드스니펫] Ajax 퀴즈1**
        
        ```html
        <!doctype html>
        <html lang="ko">
        
        <head>
            <meta charset="UTF-8">
            <title>JQuery 연습하고 가기!</title>
            <!-- JQuery를 import 합니다 -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
        
            <style type="text/css">
                div.question-box {
                    margin: 10px 0 20px 0;
                }
        
                table {
                    border: 1px solid;
                    border-collapse: collapse;
                }
        
                td,
                th {
                    padding: 10px;
                    border: 1px solid;
                }
            </style>
        
            <script>
                function q1() {
                    // 여기에 코드를 입력하세요
                }
            </script>
        
        </head>
        
        <body>
            <h1>jQuery + Ajax의 조합을 연습하자!</h1>
        
            <hr />
        
            <div class="question-box">
                <h2>2. 서울시 OpenAPI(실시간 따릉기 현황)를 이용하기</h2>
                <p>모든 위치의 따릉이 현황을 보여주세요</p>
                <p>업데이트 버튼을 누를 때마다 지웠다 새로 씌여져야 합니다.</p>
                <button onclick="q1()">업데이트</button>
                <table>
                    <thead>
                        <tr>
                            <td>거치대 위치</td>
                            <td>거치대 수</td>
                            <td>현재 거치된 따릉이 수</td>
                        </tr>
                    </thead>
                    <tbody id="names-q1">
                        <tr>
                            <td>102. 망원역 1번출구 앞</td>
                            <td>22</td>
                            <td>0</td>
                        </tr>
                        <tr>
                            <td>103. 망원역 2번출구 앞</td>
                            <td>16</td>
                            <td>0</td>
                        </tr>
                        <tr>
                            <td>104. 합정역 1번출구 앞</td>
                            <td>16</td>
                            <td>0</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </body>
        
        </html>
        ```
        
    - **[코드스니펫] Ajax 퀴즈1(보기1)**
        
        ```python
        http://spartacodingclub.shop/ajaxquiz/02_1
        ```
        
    - **[코드스니펫] Ajax 퀴즈1(완성1)**
        
        ```jsx
        <!doctype html>
        <html lang="ko">
        
        <head>
            <meta charset="UTF-8">
            <title>jQuery 연습하고 가기!</title>
            <!-- jQuery를 import 합니다 -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
        
            <style type="text/css">
                div.question-box {
                    margin: 10px 0 20px 0;
                }
        
                table {
                    border: 1px solid;
                    border-collapse: collapse;
                }
        
                td,
                th {
                    padding: 10px;
                    border: 1px solid;
                }
            </style>
        
            <script>
                function q1() {
                    $('#names-q1').empty();
                    $.ajax({
                        type: "GET",
                        url: "http://spartacodingclub.shop/sparta_api/seoulbike",
                        data: {},
                        success: function (response) {
                            let rows = response["getStationList"]["row"];
                            for (let i = 0; i < rows.length; i++) {
                                let rack_name = rows[i]['stationName'];
                                let rack_cnt = rows[i]['rackTotCnt'];
                                let bike_cnt = rows[i]['parkingBikeTotCnt'];
                                let temp_html = `<tr>
                                                    <td>${rack_name}</td>
                                                    <td>${rack_cnt}</td>
                                                    <td>${bike_cnt}</td>
                                                </tr>`
                                $('#names-q1').append(temp_html);
                            }
                        }
                    })
                }
            </script>
        
        </head>
        
        <body>
            <h1>jQuery +Ajax의 조합을 연습하자!</h1>
        
            <hr />
        
            <div class="question-box">
                <h2>2. 서울시 OpenAPI(실시간 따릉이 현황)를 이용하기</h2>
                <p>모든 위치의 따릉이 현황을 보여주세요</p>
                <p>업데이트 버튼을 누를 때마다 지웠다 새로 씌여져야 합니다.</p>
                <button onclick="q1()">업데이트</button>
                <table>
                    <thead>
                        <tr>
                            <td>거치대 위치</td>
                            <td>거치대 수</td>
                            <td>현재 거치된 따릉이 수</td>
                        </tr>
                    </thead>
                    <tbody id="names-q1">
                    </tbody>
                </table>
            </div>
        </body>
        
        </html>
        ```
        
    

## 12**. Quiz_Ajax 연습하기(2)**

<aside>
👉 [한걸음 더]
따릉이 대수가 5대 미만인 곳은 빨갛게 보여주면 어떨까요?

</aside>

- **[코드스니펫] Ajax 퀴즈1(보기2)**
    
    ```python
    http://spartacodingclub.shop/ajaxquiz/02_2
    ```
    
- **[코드스니펫] Ajax 퀴즈1(완성2)**
    
    ```jsx
    <!doctype html>
    <html lang="ko">
    
    <head>
        <meta charset="UTF-8">
        <title>jQuery 연습하고 가기!</title>
        <!-- jQuery를 import 합니다 -->
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    
        <style type="text/css">
            div.question-box {
                margin: 10px 0 20px 0;
            }
    
            table {
                border: 1px solid;
                border-collapse: collapse;
            }
    
            td,
            th {
                padding: 10px;
                border: 1px solid;
            }
    
            .urgent {
                color: red;
                font-weight: bold;
            }
        </style>
    
        <script>
            function q1() {
                $('#names-q1').empty();
                $.ajax({
                    type: "GET",
                    url: "http://spartacodingclub.shop/sparta_api/seoulbike",
                    data: {},
                    success: function (response) {
                        let rows = response["getStationList"]["row"];
                        for (let i = 0; i < rows.length; i++) {
                            let rack_name = rows[i]['stationName'];
                            let rack_cnt = rows[i]['rackTotCnt'];
                            let bike_cnt = rows[i]['parkingBikeTotCnt'];
                            let temp_html = '';
                            if (bike_cnt < 5) {
                                temp_html = `<tr class="urgent">
                                    <td>${rack_name}</td>
                                    <td>${rack_cnt}</td>
                                    <td>${bike_cnt}</td>
                                  </tr>`
                            } else {
                                temp_html = `<tr>
                                    <td>${rack_name}</td>
                                    <td>${rack_cnt}</td>
                                    <td>${bike_cnt}</td>
                                  </tr>`
                            }
                            $('#names-q1').append(temp_html);
                        }
                    }
                })
            }
        </script>
    
    </head>
    
    <body>
        <h1>jQuery+Ajax의 조합을 연습하자!</h1>
    
        <hr />
    
        <div class="question-box">
            <h2>2. 서울시 OpenAPI(실시간 따릉이 현황)를 이용하기</h2>
            <p>모든 위치의 따릉이 현황을 보여주세요</p>
            <p>업데이트 버튼을 누를 때마다 지웠다 새로 씌여져야 합니다.</p>
            <button onclick="q1()">업데이트</button>
            <table>
                <thead>
                    <tr>
                        <td>거치대 위치</td>
                        <td>거치대 수</td>
                        <td>현재 거치된 따릉이 수</td>
                    </tr>
                </thead>
                <tbody id="names-q1">
                </tbody>
            </table>
        </div>
    </body>
    
    </html>
    ```
    

## **13. Quiz_Ajax 연습하기(3)**

- 1) ✍랜덤 르탄이 API를 이용하기
    
    <aside>
    👻 힌트 : 이미지 바꾸기 / 텍스트 바꾸기
    
    </aside>
    
    - 이미지 바꾸기 : `$("#아이디값").attr("src", 이미지URL);`
    - 텍스트 바꾸기 : `$("#아이디값").text("바꾸고 싶은 텍스트");`
    - **[코드스니펫] 르탄이 API**
        
        ```html
        http://spartacodingclub.shop/sparta_api/rtan
        ```
        
    - **[코드스니펫] Ajax 퀴즈2**
        
        ```html
        <!doctype html>
        <html lang="ko">
          <head>
            <meta charset="UTF-8">
            <title>JQuery 연습하고 가기!</title>
            <!-- JQuery를 import 합니다 -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
            
            <style type="text/css">
              div.question-box {
                margin: 10px 0 20px 0;
              }
              div.question-box > div {
                margin-top: 30px;
              }
              
            </style>
        
            <script>
              function q1() {
                // 여기에 코드를 입력하세요
              }
            </script>
        
          </head>
          <body>
            <h1>JQuery+Ajax의 조합을 연습하자!</h1>
        
            <hr/>
        
            <div class="question-box">
              <h2>3. 르탄이 API를 이용하기!</h2>
              <p>아래를 르탄이 사진으로 바꿔주세요</p>
              <p>업데이트 버튼을 누를 때마다 지웠다 새로 씌여져야 합니다.</p>
              <button onclick="q1()">르탄이 나와</button>
              <div>
                <img id="img-rtan" width="300" src="http://spartacodingclub.shop/static/images/rtans/SpartaIcon11.png"/>
                <h1 id="text-rtan">나는 ㅇㅇㅇ하는 르탄이!</h1>
              </div>
            </div>
          </body>
        </html>
        ```
        
    - **[코드스니펫] Ajax 퀴즈2(보기)**
        
        ```python
        http://spartacodingclub.shop/ajaxquiz/08
        ```
        
    - **[코드스니펫] Ajax 퀴즈2(완성)**
        
        ```jsx
        <!doctype html>
        <html lang="ko">
          <head>
            <meta charset="UTF-8">
            <title>JQuery 연습하고 가기!</title>
            <!-- JQuery를 import 합니다 -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
            
            <style type="text/css">
              div.question-box {
                margin: 10px 0 20px 0;
              }
              div.question-box > div {
                margin-top: 30px;
              }
              
            </style>
        
            <script>
              function q1() {
                $.ajax({
                  type: "GET",
                  url: "http://spartacodingclub.shop/sparta_api/rtan",
                  data: {},
                  success: function(response){
                      let imgurl = response['url'];
                      $("#img-rtan").attr("src", imgurl);
        
                      let msg = response['msg'];
                      $("#text-rtan").text(msg);
                    }
                  })
              }
            </script>
        
          </head>
          <body>
            <h1>JQuery+Ajax의 조합을 연습하자!</h1>
        
            <hr/>
        
            <div class="question-box">
              <h2>3. 르탄이 API를 이용하기!</h2>
              <p>아래를 르탄이 사진으로 바꿔주세요</p>
              <p>업데이트 버튼을 누를 때마다 지웠다 새로 씌여져야 합니다.</p>
              <button onclick="q1()">르탄이 나와</button>
              <div>
                <img id="img-rtan" width="300" src="http://spartacodingclub.shop/static/images/rtans/SpartaIcon11.png"/>
                <h1 id="text-rtan">나는 ㅇㅇㅇ하는 르탄이!</h1>
              </div>
            </div>
          </body>
        </html>
        ```
