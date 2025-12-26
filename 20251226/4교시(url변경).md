request에서 url을 관리한다는 개념

```
// server.mjs
import { createServer } from 'node:http';
import { text } from './main.js';

const server = createServer((req, res) => {
  res.writeHead(200, { 
    'Content-Type': 'text/html; charset=utf-8'
});

if(req.url === "/a") {
    res.end("<h2>A 주소 화면 입니다. </h2>");
} else {
    const txt = text();
    res.end(txt);
}
});

// starts a simple http server locally on port 3000
server.listen(3000, '127.0.0.1', () => {
  console.log('Listening on 127.0.0.1:3000');
});
```

근데 얘도 너무 기니까 controller을 사용함

index.js
```
// server.mjs
import { createServer } from 'node:http';
import { controller } from './main.js';

const server = createServer((req, res) => {
  res.writeHead(200, { 
    'Content-Type': 'text/html; charset=utf-8'
});
    const html = controller(req);
    res.end(html);
});

// starts a simple http server locally on port 3000
server.listen(3000, '127.0.0.1', () => {
  console.log('Listening on 127.0.0.1:3000');
});
```

main.js
```
function text() {
    let html = "";

    html += "<h1>html 입니다.</h1>";
    html += "<p>node service ...</p>";

    return html;
}

export function controller(req) {

    let html = "";

    if(req.url === "/a") {
        html = "<h2>A 주소 화면입니다. </h2>";
    } else if(req.url === "/b") {
        html = "<h2>B 주소 화면입니다. </h2>";
    } else {
        html = text();
    }

    return html;
}
```
- `if(req.url === "/a") {` 같은 애들을 `main.js`로 옮겨주고
- `index.html`에서는 `import`하는 대상을 `text`가 아닌 `controller`로 한다
- 추가로 핵심적인 개념은 이거다. (request와 respond를 이해해야 한다)
  ```
      const html = controller(req);
    res.end(html);
  ```
  
**uri의 형식이 아닌 url을 사용. 또, uri는 정적파일로 대상까지만 가는건데 그것은 path로만 사용하는 것이 핵심**
