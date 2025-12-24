```
$(document).ready(() => {


    const html = `
      <div class="bg2"></div>
      <div class="bg1"></div>
      <div class="bg2"></div>
      <div class="bg1"></div>
      <div class="bg2"></div>

      <div class="bg1"></div>
      <div class="bg2"></div>
      <div class="bg1"></div>
      <div class="bg2"></div>
      <div class="bg1"></div>

      <div class="bg2"></div>
      <div class="bg1"></div>
      <div class="bg2"></div>
      <div class="bg1"></div>
      <div class="bg2"></div>

      <div class="bg1"></div>
      <div class="bg2"></div>
      <div class="bg1"></div>
      <div class="bg2"></div>
      <div class="bg1"></div>

      <div class="bg2"></div>
      <div class="bg1"></div>
      <div class="bg2"></div>
      <div class="bg1"></div>
      <div class="bg2"></div>` ;

    $("section").html(html);

});
```
- 얘를 줄이기 위해서 하기와 같이 줄인다

```
$(document).ready(() => {


    function view1() {
        var html = "";
        for(let i = 0 ; i < 25; i++ ) {
            let css = "1";
            if( i% 2 === 0) css = "2"
            html += `<div class="bg${css}"></div>`;
        }
    $("section").html(html);
    }

    $("button").click(function(e) {
        console.log(e);

    });

});
```
- 이 때 모든 버튼 눌러보고 콘솔에서 펼쳐서 다 똑같은 button으로 인식함

```
console.log(e.target);
```
- target을 붙이면 그리기/비우기/만능버튼 구분이 됨
- 추가로 첫번째 버튼(그리기)만 실행시킬 때 하기와 같이 코드 작성함

```
$(document).ready(() => {


    function view1() {
        var html = "";
        for(let i = 0 ; i < 25; i++ ) {
            let css = "1";
            if( i% 2 === 0) css = "2"
            html += `<div class="bg${css}"></div>`;
        }
    $("section").html(html);
    }

    $("button").click(function(e) {
        console.log(e.target);
        const index = $("button").index(e.target);
        if(index === 0) {
            view1()
        }

    });

});
```
