```
npm install styled-components

import styled from 'styled-components';
```



```
npm install node-sass


```

브라우저는 SASS 문법 모른다

SASS로 작성한 파일을 다시 CSS로 컴파일해야한다.(node-sass 설치하면 알아서 해준다)



```
@import './reset.scss';
```





animation

```
npm install react-transition-group
```

```
import { CSSTransition } from "react-transition-group";
```

컴포넌트 등장/업데이트 시 transition 쉽게쉽게 해줄 수 있음

1. <CSSTransition>으로 애니메이션 필요한 곳 감싸기
2. in, classNamse, timeout 넣기
3. class로 애니메이션 넣기
4. 원할 때 스위치 켜기
