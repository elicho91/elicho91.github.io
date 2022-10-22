---
layout: post
title: 스파르타코딩클럽 웹개발 종합반 - 2주차
subtitle: 2주차 과제
tags: [Ajax, jQuery]
comments: true
---

## **1주차 과제에 온도 추가하기**

<html lang="en">

<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
crossorigin="anonymous">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
crossorigin="anonymous"></script>

<title>BoA 팬명록</title>
<link href="https://fonts.googleapis.com/css2?family=Gowun+Dodum&display=swap" rel="stylesheet">

<style>
* {
font-family: 'Gowun Dodum', sans-serif;
}

.mypic {

width: 100%;
height: 300px;

background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url("https://i.ibb.co/SwDj2YJ/BoA.jpg");
background-position: center 20%;
background-size: cover;

color: white;

display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
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
<script>
$(document).ready(function () {
alert('로딩이 완료되었습니다.')
});

$.ajax({
type: "GET",
url: "http://spartacodingclub.shop/sparta_api/weather/incheon",
data: {},
success: function (response) {
    let temp = response["temp"];
    $('#temp').text(temp)

}
})

</script>

</head>

<body>
<div class="mypic">
<h1>BoA 방명록</h1>
<p>현재기온 : <span id="temp">0</span>°</p>
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
<p>노래 너무 좋아요!</p>
<footer class="blockquote-footer">카레빵맨</footer>
</blockquote>
</div>
</div>
<div class="card">
<div class="card-body">
<blockquote class="blockquote mb-0">
<p>누나 너무 예뻐요~!</p>
<footer class="blockquote-footer">식빵맨</footer>
</blockquote>
</div>
</div>
</div>


</body>

</html>

- 소스코드
- 
```html
<html lang="en">

<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
      integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
      crossorigin="anonymous">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
        crossorigin="anonymous"></script>

<title>BoA 팬명록</title>
<link href="https://fonts.googleapis.com/css2?family=Gowun+Dodum&display=swap" rel="stylesheet">

<style>
    * {
        font-family: 'Gowun Dodum', sans-serif;
    }

    .mypic {

        width: 100%;
        height: 300px;

        background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url("https://i.ibb.co/SwDj2YJ/BoA.jpg");
        background-position: center 20%;
        background-size: cover;

        color: white;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
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
<script>
    $(document).ready(function () {
        alert('로딩이 완료되었습니다.')
    });

    $.ajax({
            type: "GET",
            url: "http://spartacodingclub.shop/sparta_api/weather/incheon",
            data: {},
            success: function (response) {
                let temp = response["temp"];
                $('#temp').text(temp)

            }
        })

</script>

</head>

<body>
<div class="mypic">
<h1>BoA 방명록</h1>
<p>현재기온 : <span id="temp">0</span>°</p>
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
            <p>노래 너무 좋아요!</p>
            <footer class="blockquote-footer">카레빵맨</footer>
        </blockquote>
    </div>
</div>
<div class="card">
    <div class="card-body">
        <blockquote class="blockquote mb-0">
            <p>누나 너무 예뻐요~!</p>
            <footer class="blockquote-footer">식빵맨</footer>
        </blockquote>
    </div>
</div>
</div>


</body>

</html>
```
