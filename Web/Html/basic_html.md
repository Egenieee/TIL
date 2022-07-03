# Basic Html

### 🖥 웹 기본 기술
* 웹 페이지는 `HTML`, `CSS`, `JavaScript`로 표현된다.
  * 세 가지 언어를 이용해서 HTML 파일을 만들어 웹 브라우저 상에 로드하는 것 !
* 클라이언트 - 서버 관계를 간단히 말하면 다음과 같다.
  * 클라이언트는 서버에게 html 파일을 요청하고, 서버는 요청 받은 파일을 다시 클라이언트에 넘겨주게 된다.

<br>

### 📄 Html 언어
* html 언어는 표기할 내용을 여러 가지의 다양한 태그로 감싼 형태로 작성한다. 
* 다음의 예시를 보자. **b** 태그는 태그 사이에 있는 내용을 **bold** 로 표시하란 뜻의 태그이다.
```html
<b>Hello, World !</b>
```
  * `<b>` : (여는) 태그(tag)
  * `Hello World !` : 표기할 내용
  * `</b>` : (닫는) 태그(tag)

<br>

### ⚙️ Attribute 값
* 태그에는 1개 이상의 **속성(attribute)** 을 넣을 수 있다.
* 태그와 속성 사이, 속성과 속성 사이에는 한 칸의 `space` 를 두자.
* 다음의 예시를 보자. 테이블을 만들 때, **border** 에 숫자 값을 넣으면 숫자 값에 따라 표의 굵기가 정해진다.
```html
<table border='1' style='border-collapse:collapse;'>
```
* `table` : 태그(tag)
* `border='1'` : 속성(attribute)
  * `border` : 속성 이름
  * `1` : 속성 값

<br>

### 🧱️ Html 기본 구조
* 웹 페이지는 다음과 같은 html 기본 구조를 가진다.
```html
<!DOCTYPE html>  - - - > 이 문서는 html 언어로 작성되었다는 것을 알려줌
<html> - - - - - - - - > 여기서 부터 html 문서 시작 
  <head> - - - - - - - > 문서의 전체적인 정보 기록 (ex. 저자, 제목 등)
  </head>
  <body> - - - - - - - > 웹에 로드될 실제 내용 시작 
  </body>
</html>
```
  