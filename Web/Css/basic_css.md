# Basic Css

### 🎨 Css 언어
* 쉽게 말해 Html 문서를 예쁘게 꾸며주는 언어이다.
  * html 로는 웹 페이지의 구조를 잡고, 그 구조를 보기 좋게 꾸며주는 역할을 하는 것이 css !

<br>

### 💡 Css 언어 적용하는 3가지 방법
1. 적용할 태그 안에 style 속성으로 넣기 ⇨ 해당 태그에만 적용된다.
2. Html 문서 `<head>` 태그 안에 `<style>` 태그로 넣기 ⇨ 전체 문서에 적용된다.
3. Html 문서 `<head>` 태그 안에 css 파일로 링크하기 ⇨ 전체 문서에 적용된다. 

<br>

#### 1️⃣ 적용할 태그 안에 style 속성으로 넣기
스타일을 적용하고자 하는 태그에 직접 style 속성을 이용하여 스타일을 적용한다.
```html
<p style="text-align:center;color:olive">
```
* `text-align`, `color` : 프로퍼티
* `center`, `olive` : 값 
* 프로퍼티, 값이 위와 같이 연속해서 여러 번 나오면 `;` 로 구분해주자.

<br>

#### 2️⃣ Html 문서 `<head>` 태그 안에 `<style>` 태그로 넣기
태그나 클래스에 style 태그를 이용하여 스타일을 적용한다. 
```html
<head>
    <style type="text/css">
        .course {
            font-size:12px;
        }
        p {
            font-size:14px;
        }
    </style>
</head>
```
* `.course {...}` : course class 에는 12px의 폰트 사이즈를 적용시키겠다 !
* `p {...}` : p 태그에는 12px의 폰트 사이즈를 적용시키겠다 !

⇩ 위에 정의한 스타일은 `<body>` 부분에서 적용된다 ⇩
```html
<h3 class="course">Hello World !</h3>
```
* `<head>` 에서 선언한 `class` 를 원하는 태그에 적용할 수 있다.

<br>

#### 3️⃣ Html 문서 `<head>` 태그 안에 css 파일로 링크하기
css 내용이 너무 많을 때는 별도의 **css 파일**을 작성하여 **링크**하는 방법을 사용한다.
```html
<head>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
```
* `style.css` : css 파일 위치
* ⭐️모던 프론트엔드에서는 이 방법을 가장 많이 사용한다.⭐️
