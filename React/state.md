# STATE 활용



```
import React, { useState } from 'react';

function App(){
	let [따봉, 따봉변경] = useState(0);

      <div className="list">
        <h3>{ 글제목[0] } <span onClick={ () => { 따봉변경(따봉 + 1)}}>👍</span> { 따봉 }</h3>
        <p>2월 17일 발행</p>
        <hr/>
      </div>
```

* 주의:  onClick  - C 대문자로 해야한다.
* state를 직접 변경하는 것이 아니라 state 변경을 활용해야한다.



- State 변경 - deep copy 하는 법 - ... 붙이기

  ```
  var newArray = [...글제목];
  ```

  

- 정렬하기

```
  function 가나다정렬하기() {
    const newArray2 = [...글제목];
    글제목변경( newArray2.sort() );
      
  }
  
  <button onClick={ 가나다정렬하기 } >두번째 순서 정렬하기</button>

```

