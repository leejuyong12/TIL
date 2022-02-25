# router



```
npm install react-router-dom@5
```

6버전이 나왔다.



index.js

BrowserRouter는 서버로 전달될 수도 있음

```
import { BrowserRouter } from 'react-router-dom';

<BrowserRouter>
	<App />
</BrowserRouter>
```



Hashrouter 는 라우팅을 안전하게 할 수 있게 도와줌

사이트 주소 뒤에 # 이 붙는데 # 뒤에 적는 것은 서버로 전달되지 않는다.

```
import { HashRouter } from 'react-router-dom';

<HashRouter>
	<App />
</HashRouter>
```





App.js

```
import { Link, Route, Switch } from 'react-router-dom';
```

```
      <Route path="/">
        <div>메인페이지에요</div>
      </Route>
      <Route path="/detail">
        <div>디테일페이지에요</div>
      </Route>
```

이렇게 했을때 메인페이지에요 디테일페이지에요 다 보이는 이유는 router는 일치하는 거 다 보여주는 속성이 있다. 그래서 정확히 하나만 보여주려고 하면

```
      <Route exact path="/">
        <div>메인페이지에요</div>
      </Route>
      <Route path="/detail">
        <div>디테일페이지에요</div>
      </Route>
```

exact 추가하기