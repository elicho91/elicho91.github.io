---
layout: post
title: 스파르타코딩클럽 웹개발 종합반 - 2주차
subtitle: 2-2
tags: [JSON, Ajax]
comments: true
---

## **서버-클라이언트 통신 이해하기**

- 1) 서버→클라이언트: "JSON"을 이해하기
    - 서울시 OpenAPI에 접속해보기
        - **[코드스니펫] 서울시 OpenAPI**
            
            ```html
            http://openapi.seoul.go.kr:8088/6d4d776b466c656533356a4b4b5872/json/RealtimeCityAir/1/99
            ```
            
    - 크롬 익스텐션 JSONView를 설치.
        - **Jsonview**
            
            ```html
            https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=ko
            ```
            
    - JSON은, Key:Value로 이루어져 있다. (자료형 Dictionary와 유사)
        
        <aside>
        👉 위 예제에서는 RealtimeCityAir라는 키 값에 딕셔너리 형 value가 들어가있고,
        그 안에 row라는 키 값에는 리스트형 value가 들어있다.
        
        </aside>
        
        ![Untitle](https://teamsparta.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F8f29b7c4-6b71-4b7f-9013-a8afb772dd1a%2FUntitled.png?table=block&id=ffdcb262-43b5-49bf-b394-267442b39534&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=1150&userId=&cache=v2)
        
- 2) 클라이언트→서버: GET 요청 이해하기
    
    <aside>
    👉 **API는 은행 창구와 같은 것!**
    
    같은 예금 창구에서도 개인 고객이냐 기업 고객이냐에 따라
    가져와야 하는 것 / 처리해주는 것이 다른 것처럼,
    
    클라이언트가 요청 할 때에도, "타입"이라는 것이 존재한다.
    
    * GET        →      통상적으로! 데이터 조회(Read)를 요청할 때
                               예) 영화 목록 조회
    
    * POST     →      통상적으로! 데이터 생성(Create), 변경(Update), 삭제(Delete) 요청 할 때
                               예) 회원가입, 회원탈퇴, 비밀번호 수정
    
    이 중에서 오늘은 GET 방식에 대해 배워보겠습니다. (POST는 4주차에 배웁니다)
    
    </aside>
    
    - **GET**
        
        [기생충](https://movie.naver.com/movie/bi/mi/basic.nhn?code=161967)
        
        ```jsx
        https://movie.naver.com/movie/bi/mi/basic.nhn?code=161967
        
        "?" 기준으로 앞부분이 <서버 주소>, 뒷부분이 [영화 번호] 입니다.
        
        * 서버 주소: https://movie.naver.com/movie/bi/mi/basic.nhn
        * 영화 정보: code=161967
        ```
        
        <aside>
        👉 **GET 방식으로 데이터를 전달하는 방법**
        
        ?  : 여기서부터 전달할 데이터가 작성된다는 의미.
        & : 전달할 데이터가 더 있다는 뜻입니다.
        
        예시) google.com/search?q=아이폰&sourceid=chrome&ie=UTF-8
        
                 위 주소는 google.com의 search 창구에 다음 정보를 전달!
                 q=아이폰                        (검색어)
                 sourceid=chrome        (브라우저 정보)
                 ie=UTF-8                      (인코딩 정보)
        
        </aside>
        

## **Ajax 시작하기**

- 1) Ajax 시작하기
        

- **미세먼지 OpenAPI**


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
          data: {}, // 요청하면서 함께 줄 데이터 (GET 요청시엔 공란)
          success: function(response){ // 서버에서 준 결과를 response라는 변수에 담음
            console.log(response) // 서버에서 준 결과를 이용해서 나머지 코드를 작성
          }
        })
        ```
        
    - $ajax 코드 설명
        - type: "GET" → GET 방식으로 요청한다.
        - url: 요청할 url
        - data: 요청하면서 함께 줄 데이터 (GET 요청시엔 공란)
            
            <aside>
            👉 리마인드
            GET 요청은, url뒤에 아래와 같이 붙여서 데이터를 가져간다.
            http://naver.com?param=value&param2=value2 
            
            POST 요청은, data : {} 에 넣어서 데이터를 가져간다.
            data: { param: 'value', param2: 'value2' },
            
            </aside>
            
        - success: 성공하면, response 값에 서버의 결과 값을 담아서 함수를 실행!
            

            
            ```jsx
            success: function(response){ // 서버에서 준 결과를 response라는 변수에 담음
              console.log(response) 
            }
            ```
            
- 2) Ajax 통신의 결과값을 이용해보기


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
                
                ![Untitle](https://teamsparta.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fcf6e770d-9618-4c1d-beef-afb23b3cd2c9%2FUntitled.png?table=block&id=5a4d82fc-9704-44d0-8c82-6957b2259345&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=480&userId=&cache=v2)
                
                위 그림과 같이 RealtimeCityAir > row 에 미세먼지 데이터가 들어있음.
                
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
                
                ![Untitle](https://teamsparta.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fdc6ab951-95aa-4415-8977-fc988e04e3cc%2FUntitled.png?table=block&id=d8a50140-85db-4d2e-b3cc-799dcd4e37d0&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=480&userId=&cache=v2)
                
                row의 값을 mise_list에 담고 반복문 돌리기!
                
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
                
                ![Untitle](https://teamsparta.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F41a0dbc3-2ad1-458f-baeb-08961f950b25%2FUntitled.png?table=block&id=c5196d3f-1dcd-4370-9d4d-59e97cb6e900&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=480&userId=&cache=v2)
                
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
