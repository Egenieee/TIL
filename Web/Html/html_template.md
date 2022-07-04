# Html Template

### 🗃 Html5 기본 템플릿
* html:5`tab`을 입력하면, 아래와 같이 자동으로 **기본 html5 코드**가 작성된다.

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

⇩ 아래처럼 기본 템플릿 코드를 조금 더 확장해서 한 코드씩 이해해보자. ⇩

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="description" content="HTML 연습이당">
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
* Html 문서는 최상단에 위와 같은 태그를 사용해야 한다. **"이 문서는 HTML 언어를 사용한다."** 라고 말해주는 시작 태그이다. 닫는 태그 없이 단독으로 쓰인다.

<br>

### html
```html
<html lang="ko"></html>
```
* 위 태그부터 html 문서가 시작된다. 본 태그는 **문서 범위 설정 태그**로 html 문서는 이 태그 안에 작성되어야 하고, 맨 마지막에는 닫는 html 태그로 닫아줘야 한다. 
* 이 태그에 들어가는 속성 값은 아래와 같다.
    |attribute|description|values|
    |:---|:---|:---|
    |lang|문서 언어 설정(ISO 639-1)|**ko**(한국어), en(영어) 등|

<br>

### head
```html
<head>
    여기에 html 문서 전체를 아우르는 정보를 담는다잉.
</head>
```
* `<head>` 태그 안에는 html 문서 전체를 대표하거나, html 문서에서 필요한 데이터를 넣는다.
  * `<head>` 태그 안에서 주용 사용되는 태그는 아래와 같다.
    |tag|description|
    |:---|:---|
    |title|html 문서 제목 ; 주로 해당 웹페이지를 보여주는 웹브라우저 상단에 표시|
    |meta|html 문서 전체를 대표하는 정보를 넣는데 사용|

<br>

### body
```html
<body>
    여기엔 웹 페이지를 들어갔을 때 보이는 내용들을 담는다잉.
</body>
```
* `<body>` 태그 안에는 html 문서에 표시되는 내용을 넣는다. 

<br>

### meta
```html
<meta>
```
* 전반적인 문서 정보를 표시하기 위한 설정
* 메타 태그에 들어가는 주요 속성은 아래와 같다.
    |attribute|description|values|
    |:---|:---|:---|
    |charset|문자 인코딩 설정|utf-8(유니코드), euc-kr(한국어) 등|
    |name|메타 정보 이름|**description**: html 문서 설명, **author**: 저자 이름 등|

<br>

#### 주요 meta name values
```html
<meta name="description" content="HTML 연습이당">
<meta name="keywords" content="HTML, CSS, JAVSCRIPT">
<meta name="author" content="e.genieee">
```

<br>

#### 호환성 관련 meta 태그
```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```
* 인터넷 익스플로러에서 최신 표준 모드로 렌더링되도록 하는 설정
* 인터넷 익스플로러(IE)의 호환성 문제로 기본적으로 위의 코드는 html 문서에 포함되는 것이 좋다.

<br>

#### 반응형 웹 관련 태그
```html
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```
* 위의 코드는 **반응형 웹**에 관련한 코드이다. 
* 화면에 보이는 직사각형 영역이 **확대**, **축소**를 하면 깨지게 되니까, 초기 설정을 정확히 하는 부분이라고 생각하면 된다. 
* **viewport (뷰포트)란?**
  * 현재 화면에 보여지고 있는 영역으로 이야기한다. 웹브라우저 상에서는 현재 윈도우에서 문서를 볼 수 있는 전체 화면을 의미한다.
* **meta viewport** 설정
  * 초기 뷰포트에 대한 설정을 의미한다. 주로 확대, 축소를 하지 못하게끔 위와 같은 코드처럼 설정한다. 
    |attribute|description|values|
    |:---|:---|:---|
    |width|초기 뷰포트 너비 설정|**device-width**(현재 사용하고 있는 디바이스의 너비) or 양의 정수(특정 너비)|
    |user-scalable|웹 페이지 확대 허용 여부 설정|**no** or yes ; default는 yes 지만, 사용자가 임의로 확대, 축소 할 수 업게끔 no로 설정하는 경우가 대다수)|
    |initial-scale|디바이스 너비와 뷰포트 너비 비율 설정|0.0 ~ 10.0 사이 수 (주로 **100%** 인 **0.1**로 나타냄)|
    |maximum-scale|최대 확대 비율 설정|0.0 ~ 10.0 사이 수 (주로 **100%** 인 **0.1**로 나타냄)|
    |minimum-scale|최소 확대 비율 설정|0.0 ~ 10.0 사이 수 (주로 **100%** 인 **0.1**로 나타냄)|

<br>

### link
```html
<link rel="stylesheet" href="css/styles.css" />
<link rel="icon" href="favicon.png" />
```
* html 문서에 필요한 외부 데이터를 가져오기 위해 사용 ⇨ 주로 **css 파일**과 **아이콘 파일**을 가져오기 위해 사용한다.
* 링크 태그에 들어가는 주요 속성은 아래와 같다. 
    |attribute|description|values|
    |:---|:---|:---|
    |rel|html 문서와 외부 데이터와의 관계 표시|**stylesheet**(css 파일), **icon**(아이콘 파일) 등|
    |href|외부 데이터 파일 위치 지정|파일 경로 (상대 경로 또는 절대 경로로 설정)|

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
* css 코드를 html 문서 내에서 작성할 때 사용한다. 
* css 코드를 적용할 때는 file 형태로 `<link>` 태그를 사용해서 가져오거나 `<style>` 태그를 사용해 직접 html 문서에 넣을 수 있다.

<br>

### script
* javascript 코드를 적용할 때는 file 형태로 `<link>` 태그를 사용해서 가져오거나 `<script>` 태그를 사용해 javascript 코드를 직접 html 문서에 넣을 수 있다.

**`<link>` 태그 이용하는 방법 (가장 일반적인 사용법)**
```html
<script src="js/main.js"></script>
```
<br>

**`<script>` 태그 이용하는 방법**
```html
<script type="text/javascript">
    JS 코드 ~ 블라블라 
</script>
```

**html5**에서는 위와 같이 안쓰고 아래처럼 `<script>`만 쓰면 된다
```html
<script>
    JS 코드 ~ 블라블라 
</script>
```