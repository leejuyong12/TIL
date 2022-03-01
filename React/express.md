## express



새로운 작업폴더에

```
server.js

const express = require('express');
const path = require('path');
const app = express();

const http = require('http').createServer(app);
http.listen(8080, function () {
  console.log('listening on 8080')
}); 
```

express 라이브러리 설치



```
npm init
```

```
npm install express
```

```
서버실행은


node server.js

혹은

nodemon server.js
```



