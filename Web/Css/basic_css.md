# Basic Css

### ๐จ Css ์ธ์ด
* ์ฝ๊ฒ ๋งํด Html ๋ฌธ์๋ฅผ ์์๊ฒ ๊พธ๋ฉฐ์ฃผ๋ ์ธ์ด์ด๋ค.
  * html ๋ก๋ ์น ํ์ด์ง์ ๊ตฌ์กฐ๋ฅผ ์ก๊ณ , ๊ทธ ๊ตฌ์กฐ๋ฅผ ๋ณด๊ธฐ ์ข๊ฒ ๊พธ๋ฉฐ์ฃผ๋ ์ญํ ์ ํ๋ ๊ฒ์ด css !

<br>

### ๐ก Css ์ธ์ด ์ ์ฉํ๋ 3๊ฐ์ง ๋ฐฉ๋ฒ
1. ์ ์ฉํ  ํ๊ทธ ์์ style ์์ฑ์ผ๋ก ๋ฃ๊ธฐ โจ ํด๋น ํ๊ทธ์๋ง ์ ์ฉ๋๋ค.
2. Html ๋ฌธ์ `<head>` ํ๊ทธ ์์ `<style>` ํ๊ทธ๋ก ๋ฃ๊ธฐ โจ ์ ์ฒด ๋ฌธ์์ ์ ์ฉ๋๋ค.
3. Html ๋ฌธ์ `<head>` ํ๊ทธ ์์ css ํ์ผ๋ก ๋งํฌํ๊ธฐ โจ ์ ์ฒด ๋ฌธ์์ ์ ์ฉ๋๋ค. 

<br>

#### 1๏ธโฃ ์ ์ฉํ  ํ๊ทธ ์์ style ์์ฑ์ผ๋ก ๋ฃ๊ธฐ
์คํ์ผ์ ์ ์ฉํ๊ณ ์ ํ๋ ํ๊ทธ์ ์ง์  style ์์ฑ์ ์ด์ฉํ์ฌ ์คํ์ผ์ ์ ์ฉํ๋ค.
```html
<p style="text-align:center;color:olive">
```
* `text-align`, `color` : ํ๋กํผํฐ
* `center`, `olive` : ๊ฐ 
* ํ๋กํผํฐ, ๊ฐ์ด ์์ ๊ฐ์ด ์ฐ์ํด์ ์ฌ๋ฌ ๋ฒ ๋์ค๋ฉด `;` ๋ก ๊ตฌ๋ถํด์ฃผ์.

<br>

#### 2๏ธโฃ Html ๋ฌธ์ `<head>` ํ๊ทธ ์์ `<style>` ํ๊ทธ๋ก ๋ฃ๊ธฐ
ํ๊ทธ๋ ํด๋์ค์ style ํ๊ทธ๋ฅผ ์ด์ฉํ์ฌ ์คํ์ผ์ ์ ์ฉํ๋ค. 
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
* `.course {...}` : course class ์๋ 12px์ ํฐํธ ์ฌ์ด์ฆ๋ฅผ ์ ์ฉ์ํค๊ฒ ๋ค !
* `p {...}` : p ํ๊ทธ์๋ 12px์ ํฐํธ ์ฌ์ด์ฆ๋ฅผ ์ ์ฉ์ํค๊ฒ ๋ค !

โฉ ์์ ์ ์ํ ์คํ์ผ์ `<body>` ๋ถ๋ถ์์ ์ ์ฉ๋๋ค โฉ
```html
<h3 class="course">Hello World !</h3>
```
* `<head>` ์์ ์ ์ธํ `class` ๋ฅผ ์ํ๋ ํ๊ทธ์ ์ ์ฉํ  ์ ์๋ค.

<br>

#### 3๏ธโฃ Html ๋ฌธ์ `<head>` ํ๊ทธ ์์ css ํ์ผ๋ก ๋งํฌํ๊ธฐ
css ๋ด์ฉ์ด ๋๋ฌด ๋ง์ ๋๋ ๋ณ๋์ **css ํ์ผ**์ ์์ฑํ์ฌ **๋งํฌ**ํ๋ ๋ฐฉ๋ฒ์ ์ฌ์ฉํ๋ค.
```html
<head>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
```
* `style.css` : css ํ์ผ ์์น
* โญ๏ธ๋ชจ๋ ํ๋ก ํธ์๋์์๋ ์ด ๋ฐฉ๋ฒ์ ๊ฐ์ฅ ๋ง์ด ์ฌ์ฉํ๋ค.โญ๏ธ
