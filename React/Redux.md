# Redux

```
npm install redux react-redux
```

```
yarn add redux react-redux
```

쓰는 이유 1

props 없이 모든 컴포넌트가 state를 갖다쓰기 가능(복잡합 props전송 필요 없다)



index.js

```
import { Provider } from 'react-redux';
import { createStore } from 'redux';
let store = createStore(()=> { return [{ id: 0, name:'멋진신발', quan: 2 }] });

//store는 다른 파일에 만들어도 된다.

ReactDOM.render(
  <React.StrictMode>
    <BrowserRouter>
      <Provider store={store}>    --> 여기 넣기
        <App />
      </Provider>
    </BrowserRouter>  
  </React.StrictMode>,
  document.getElementById('root')
);
```

Cart.js

```
import { connect } from 'react-redux';

function state를props화(state){  //redux store 데이터 가져와서 props로 변환해주는 함수
    return {
        state : state
    }
}

export default connect(state를props화)(Cart)



위에는 store를 쓰겠습니다 하는 함수
```





redux에서는 state 데이터의 수정방법을 미리 정의한다.

Redux 쓰는 이유2

state 데이터 관리 가능







state가 여러개 필요하면 reducer를 더 만들기

reducer안에 state초기값 + 수정하는 법

reducer 합치려면 combineReducers({})