#study_08.html
```css
<input type="password" name="pw" />
```  
- `input` 사용시 `type` & `name` 필수<br />
- `study_08.css`에 아래와 같이 코드를 넣으면

```css
input {width: 100%}
```
- `text`, `password`, `submit`에 따라 형식이 다름

```css
* {box-sizing: border-box;}
body {margin: 0;}
input {width: 100%}
input[type=submit] {margin-top: 5px}
/* input[type=text], input[type=password] {width: clac(100% - 8px);} */
```
- `* {box-sizing: border-box;}`과 `body`,`input`을 정해주면 `calc`를 굳이 안해줘도 됨

```css
input {width: 100%; max-width: 800px; margin: 0 calc(100% - 800px);}
```
- 이게 이상하게 나오는 이유는 전체 100%가 너무 넓기 때문이다
- 해결법: 50%로 줄인다 (`width`도 `max-width`도)

```css
input {width: 100%; max-width: 800px; margin: 0 calc(50% - 400px);}
```
- 얘도 완전히 적용이 되지 않으니

```css
form {text-align: center;}
```
- 이렇게 사용하면 해결
- 핵심: 부모-자식간의 관계가 중요함
        정렬이라는 개념 `text-align: center;`
