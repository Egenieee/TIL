# Html Template

### ๐ Html5 ๊ธฐ๋ณธ ํํ๋ฆฟ
* html:5`tab`์ ์๋ ฅํ๋ฉด, ์๋์ ๊ฐ์ด ์๋์ผ๋ก **๊ธฐ๋ณธ html5 ์ฝ๋**๊ฐ ์์ฑ๋๋ค.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

โฉ ์๋์ฒ๋ผ ๊ธฐ๋ณธ ํํ๋ฆฟ ์ฝ๋๋ฅผ ์กฐ๊ธ ๋ ํ์ฅํด์ ํ ์ฝ๋์ฉ ์ดํดํด๋ณด์. โฉ

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="description" content="HTML ์ฐ์ต์ด๋น">
    <meta name="keywords" content="HTML, CSS, JAVSCRIPT">
    <meta name="author" content="e.genieee">

    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">

    <link rel="stylesheet" href="css/styles.css" />
    <link rel="icon" href="favicon.png" />

    <title>e.genieee</title>
</head>
<body>
    <script src="js/main.js"></script>
</body>
</html>
```
<br>

### DOCTYPE
```html
<!DOCTYPE html>
```
* Html ๋ฌธ์๋ ์ต์๋จ์ ์์ ๊ฐ์ ํ๊ทธ๋ฅผ ์ฌ์ฉํด์ผ ํ๋ค. **"์ด ๋ฌธ์๋ HTML ์ธ์ด๋ฅผ ์ฌ์ฉํ๋ค."** ๋ผ๊ณ  ๋งํด์ฃผ๋ ์์ ํ๊ทธ์ด๋ค. ๋ซ๋ ํ๊ทธ ์์ด ๋จ๋์ผ๋ก ์ฐ์ธ๋ค.

<br>

### html
```html
<html lang="ko"></html>
```
* ์ ํ๊ทธ๋ถํฐ html ๋ฌธ์๊ฐ ์์๋๋ค. ๋ณธ ํ๊ทธ๋ **๋ฌธ์ ๋ฒ์ ์ค์  ํ๊ทธ**๋ก html ๋ฌธ์๋ ์ด ํ๊ทธ ์์ ์์ฑ๋์ด์ผ ํ๊ณ , ๋งจ ๋ง์ง๋ง์๋ ๋ซ๋ html ํ๊ทธ๋ก ๋ซ์์ค์ผ ํ๋ค. 
* ์ด ํ๊ทธ์ ๋ค์ด๊ฐ๋ ์์ฑ ๊ฐ์ ์๋์ ๊ฐ๋ค.

|attribute|description|values|
|:---|:---|:---|
|lang|๋ฌธ์ ์ธ์ด ์ค์ (ISO 639-1)|**ko**(ํ๊ตญ์ด), en(์์ด) ๋ฑ|

<br>

### head
```html
<head>
    ์ฌ๊ธฐ์ html ๋ฌธ์ ์ ์ฒด๋ฅผ ์์ฐ๋ฅด๋ ์ ๋ณด๋ฅผ ๋ด๋๋ค์.
</head>
```
* `<head>` ํ๊ทธ ์์๋ html ๋ฌธ์ ์ ์ฒด๋ฅผ ๋ํํ๊ฑฐ๋, html ๋ฌธ์์์ ํ์ํ ๋ฐ์ดํฐ๋ฅผ ๋ฃ๋๋ค.
* `<head>` ํ๊ทธ ์์์ ์ฃผ์ฉ ์ฌ์ฉ๋๋ ํ๊ทธ๋ ์๋์ ๊ฐ๋ค.
  
|tag|description|
|:---|:---|
|title|html ๋ฌธ์ ์ ๋ชฉ ; ์ฃผ๋ก ํด๋น ์นํ์ด์ง๋ฅผ ๋ณด์ฌ์ฃผ๋ ์น๋ธ๋ผ์ฐ์  ์๋จ์ ํ์|
|meta|html ๋ฌธ์ ์ ์ฒด๋ฅผ ๋ํํ๋ ์ ๋ณด๋ฅผ ๋ฃ๋๋ฐ ์ฌ์ฉ|

<br>

### body
```html
<body>
    ์ฌ๊ธฐ์ ์น ํ์ด์ง๋ฅผ ๋ค์ด๊ฐ์ ๋ ๋ณด์ด๋ ๋ด์ฉ๋ค์ ๋ด๋๋ค์.
</body>
```
* `<body>` ํ๊ทธ ์์๋ html ๋ฌธ์์ ํ์๋๋ ๋ด์ฉ์ ๋ฃ๋๋ค. 

<br>

### meta
```html
<meta>
```
* ์ ๋ฐ์ ์ธ ๋ฌธ์ ์ ๋ณด๋ฅผ ํ์ํ๊ธฐ ์ํ ์ค์ 
* ๋ฉํ ํ๊ทธ์ ๋ค์ด๊ฐ๋ ์ฃผ์ ์์ฑ์ ์๋์ ๊ฐ๋ค.

|attribute|description|values|
|:---|:---|:---|
|charset|๋ฌธ์ ์ธ์ฝ๋ฉ ์ค์ |utf-8(์ ๋์ฝ๋), euc-kr(ํ๊ตญ์ด) ๋ฑ|
|name|๋ฉํ ์ ๋ณด ์ด๋ฆ|**description**: html ๋ฌธ์ ์ค๋ช, **author**: ์ ์ ์ด๋ฆ ๋ฑ|

<br>

#### ์ฃผ์ meta name values
```html
<meta name="description" content="HTML ์ฐ์ต์ด๋น">
<meta name="keywords" content="HTML, CSS, JAVSCRIPT">
<meta name="author" content="e.genieee">
```

<br>

#### ํธํ์ฑ ๊ด๋ จ meta ํ๊ทธ
```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```
* ์ธํฐ๋ท ์ต์คํ๋ก๋ฌ์์ ์ต์  ํ์ค ๋ชจ๋๋ก ๋ ๋๋ง๋๋๋ก ํ๋ ์ค์ 
* ์ธํฐ๋ท ์ต์คํ๋ก๋ฌ(IE)์ ํธํ์ฑ ๋ฌธ์ ๋ก ๊ธฐ๋ณธ์ ์ผ๋ก ์์ ์ฝ๋๋ html ๋ฌธ์์ ํฌํจ๋๋ ๊ฒ์ด ์ข๋ค.

<br>

#### ๋ฐ์ํ ์น ๊ด๋ จ ํ๊ทธ
```html
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```
* ์์ ์ฝ๋๋ **๋ฐ์ํ ์น**์ ๊ด๋ จํ ์ฝ๋์ด๋ค. 
* ํ๋ฉด์ ๋ณด์ด๋ ์ง์ฌ๊ฐํ ์์ญ์ด **ํ๋**, **์ถ์**๋ฅผ ํ๋ฉด ๊นจ์ง๊ฒ ๋๋๊น, ์ด๊ธฐ ์ค์ ์ ์ ํํ ํ๋ ๋ถ๋ถ์ด๋ผ๊ณ  ์๊ฐํ๋ฉด ๋๋ค. 
* **viewport (๋ทฐํฌํธ)๋?**
  * ํ์ฌ ํ๋ฉด์ ๋ณด์ฌ์ง๊ณ  ์๋ ์์ญ์ผ๋ก ์ด์ผ๊ธฐํ๋ค. ์น๋ธ๋ผ์ฐ์  ์์์๋ ํ์ฌ ์๋์ฐ์์ ๋ฌธ์๋ฅผ ๋ณผ ์ ์๋ ์ ์ฒด ํ๋ฉด์ ์๋ฏธํ๋ค.
* **meta viewport** ์ค์ 
  * ์ด๊ธฐ ๋ทฐํฌํธ์ ๋ํ ์ค์ ์ ์๋ฏธํ๋ค. ์ฃผ๋ก ํ๋, ์ถ์๋ฅผ ํ์ง ๋ชปํ๊ฒ๋ ์์ ๊ฐ์ ์ฝ๋์ฒ๋ผ ์ค์ ํ๋ค. 

|attribute|description|values|
|:---|:---|:---|
|width|์ด๊ธฐ ๋ทฐํฌํธ ๋๋น ์ค์ |**device-width**(ํ์ฌ ์ฌ์ฉํ๊ณ  ์๋ ๋๋ฐ์ด์ค์ ๋๋น) or ์์ ์ ์(ํน์  ๋๋น)|
|user-scalable|์น ํ์ด์ง ํ๋ ํ์ฉ ์ฌ๋ถ ์ค์ |**no** or yes ; default๋ yes ์ง๋ง, ์ฌ์ฉ์๊ฐ ์์๋ก ํ๋, ์ถ์ ํ  ์ ์๊ฒ๋ no๋ก ์ค์ ํ๋ ๊ฒฝ์ฐ๊ฐ ๋๋ค์)|
|initial-scale|๋๋ฐ์ด์ค ๋๋น์ ๋ทฐํฌํธ ๋๋น ๋น์จ ์ค์ |0.0 ~ 10.0 ์ฌ์ด ์ (์ฃผ๋ก **100%** ์ธ **0.1**๋ก ๋ํ๋)|
|maximum-scale|์ต๋ ํ๋ ๋น์จ ์ค์ |0.0 ~ 10.0 ์ฌ์ด ์ (์ฃผ๋ก **100%** ์ธ **0.1**๋ก ๋ํ๋)|
|minimum-scale|์ต์ ํ๋ ๋น์จ ์ค์ |0.0 ~ 10.0 ์ฌ์ด ์ (์ฃผ๋ก **100%** ์ธ **0.1**๋ก ๋ํ๋)|

<br>

### link
```html
<link rel="stylesheet" href="css/styles.css" />
<link rel="icon" href="favicon.png" />
```
* html ๋ฌธ์์ ํ์ํ ์ธ๋ถ ๋ฐ์ดํฐ๋ฅผ ๊ฐ์ ธ์ค๊ธฐ ์ํด ์ฌ์ฉ โจ ์ฃผ๋ก **css ํ์ผ**๊ณผ **์์ด์ฝ ํ์ผ**์ ๊ฐ์ ธ์ค๊ธฐ ์ํด ์ฌ์ฉํ๋ค.
* ๋งํฌ ํ๊ทธ์ ๋ค์ด๊ฐ๋ ์ฃผ์ ์์ฑ์ ์๋์ ๊ฐ๋ค. 

|attribute|description|values|
|:---|:---|:---|
|rel|html ๋ฌธ์์ ์ธ๋ถ ๋ฐ์ดํฐ์์ ๊ด๊ณ ํ์|**stylesheet**(css ํ์ผ), **icon**(์์ด์ฝ ํ์ผ) ๋ฑ|
|href|์ธ๋ถ ๋ฐ์ดํฐ ํ์ผ ์์น ์ง์ |ํ์ผ ๊ฒฝ๋ก (์๋ ๊ฒฝ๋ก ๋๋ ์ ๋ ๊ฒฝ๋ก๋ก ์ค์ )|

<br>

### style
```html
<style>
    h1 {
        font-size: 12px;
        color: olive;
        text-align:center;
    }
</style>
```
* css ์ฝ๋๋ฅผ html ๋ฌธ์ ๋ด์์ ์์ฑํ  ๋ ์ฌ์ฉํ๋ค. 
* css ์ฝ๋๋ฅผ ์ ์ฉํ  ๋๋ file ํํ๋ก `<link>` ํ๊ทธ๋ฅผ ์ฌ์ฉํด์ ๊ฐ์ ธ์ค๊ฑฐ๋ `<style>` ํ๊ทธ๋ฅผ ์ฌ์ฉํด ์ง์  html ๋ฌธ์์ ๋ฃ์ ์ ์๋ค.

<br>

### script
* javascript ์ฝ๋๋ฅผ ์ ์ฉํ  ๋๋ file ํํ๋ก `<link>` ํ๊ทธ๋ฅผ ์ฌ์ฉํด์ ๊ฐ์ ธ์ค๊ฑฐ๋ `<script>` ํ๊ทธ๋ฅผ ์ฌ์ฉํด javascript ์ฝ๋๋ฅผ ์ง์  html ๋ฌธ์์ ๋ฃ์ ์ ์๋ค.

**`<link>` ํ๊ทธ ์ด์ฉํ๋ ๋ฐฉ๋ฒ (๊ฐ์ฅ ์ผ๋ฐ์ ์ธ ์ฌ์ฉ๋ฒ)**
```html
<script src="js/main.js"></script>
```
<br>

**`<script>` ํ๊ทธ ์ด์ฉํ๋ ๋ฐฉ๋ฒ**
```html
<script type="text/javascript">
    JS ์ฝ๋ ~ ๋ธ๋ผ๋ธ๋ผ 
</script>
```

**html5**์์๋ ์์ ๊ฐ์ด ์์ฐ๊ณ  ์๋์ฒ๋ผ `<script>`๋ง ์ฐ๋ฉด ๋๋ค
```html
<script>
    JS ์ฝ๋ ~ ๋ธ๋ผ๋ธ๋ผ 
</script>
```