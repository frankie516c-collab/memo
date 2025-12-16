내가 캐치하지 못한 것 (디테일이 떨어짐)
- 폰트
- 보더
- lemon 비활성화
- Input 이랑 Name이랑 열을 맞춰야함

#iframe
- 블로그에 유투브나 지도나 웹페이지를 화면으로 보이게 가져다주는거

#선택자
```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="icon" href="../../images/logo.png"/>
	<title>선택자 사용법 1</title>
	<style>
		/* 선택자 : 태그, 아이디, 클래스 */
		span {
			color:#0f0; <-- 얘가 먼저 나왔지만 적용이 되지 않는 이유는 -->
		}
		span {
			color:#f00; <-- 얘가 뒤에 나와서 superior하게 적용되기 때문 마지막꺼가 적용됨-->
		}
		div>span {
			color:#999; <--동일한 이유로 얘가 적용이 되지 않음-->
		}
		div.first-class>span{
			background-color: #ff0; <--동일한 이유로 얘가 적용이 됨 덮어씌어짐-->
		}
		#ex span{
			background-color: aqua;
		}
		h1, h2 {
			border-style: solid;
		}
	</style>
</head>
<body>
	<div id="ex">
    <h1>Heading 1</h1>
    <h2>Heading 2-1</h2>
    <div class="first-class">
      <span>span tag1</span>
      <p>
        <span>span tag2</span>
      </p>
    </div>
    <span>span tag3</span>
  </div>
  
  <div class="second-class">
    <h2>Heading 2-2</h2>
    <span>span tag4</span>
  </div>
  
  <span>span tag5</span>
</body>
</html>
```
#선택자 study06_page2
```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="icon" href="../../images/logo.png"/>
	<title>선택자 사용법 2</title>
	<style>
		/* 
		=============================================
		= 전체 일치
		^= 시작하는
		$= 끝나는
		*= 일부 문자 (단어 중 일부 문자)
		~= 단어 일치
		=============================================
		*/
		a[href^="https"] { <---밑에 보면 해당 프로토콜에만 적용-->
			background-color: purple;
			color:#fff; <--얘가 적용되는 이유는 밑에 href$ 때문-->
		}
		a[href$="net/"]{ <--a태그 사용하고 주소 끝나는 $를 이용해 폰트 색이 적용 됨-->
			color:red;
		}
		li[title*="ip"]{ <--ip라는 글자가 들어가는거만 아쿠아로 적용-->
			color:aqua;
		}
	</style>
</head>
<body>
	<ul>
    <li><a href="https://www.daum.net/">daum</a></li>
    <li><a href="https://www.naver.com/">naver</a></li>
    <li><a href="mailto:help@host.co.kr" title="mail">help</a></li>
    <li title="lorem ipsum">Lorem ipsum dolor sit amet.</li>
    <li title="lorem">Lorem ipsum dolor sit amet.</li>
  </ul>
</body>
</html>
```
