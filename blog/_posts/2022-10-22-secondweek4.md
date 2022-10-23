---
layout: post
title: 스파르타코딩클럽 웹개발 종합반 - 2주차
subtitle: Ajax 연습하기
tags: [Ajax, Jquery]
comments: true
---

## **Ajax 연습하기 (1)**

- 1) 서울시 OpenAPI(실시간 미세먼지 상태)를 이용하기
    - **Ajax 기본 골격**

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

    - **미세먼지 OpenAPI**

        ```html
        http://spartacodingclub.shop/sparta_api/seoulair
        ```


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

- 소스코드

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

## **Ajax 연습하기 (2)**

- 1) ✍서울시 OpenAPI(실시간 따릉이 현황)을 이용하기
    - **[코드스니펫] 따릉이 OpenAPI**

        ```html
        http://spartacodingclub.shop/sparta_api/seoulbike
        ```
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

- 소스코드

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
    

## **Ajax 연습하기 (3)**

- 1) ✍랜덤 르탄이 API를 이용하기
    
    
    - 이미지 바꾸기 : `$("#아이디값").attr("src", 이미지URL);`
    - 텍스트 바꾸기 : `$("#아이디값").text("바꾸고 싶은 텍스트");`
    - **[코드스니펫] 르탄이 API**

        ```html
        http://spartacodingclub.shop/sparta_api/rtan
        ```

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

- 소스코드

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
