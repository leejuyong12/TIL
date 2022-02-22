# Props



props로 자식에게 state 전해주는 법

1. <자식컴포넌트 작명={state명}/>
2. 자식컴포넌트에서 props 파라미터 입력 후 사용

```
      {
        modal === true
        ? <Modal 글제목={ 글제목 } ></Modal>
        : null
      }
```

```
function Modal(props) {
  return( 
    <div className="modal">
      <h2>{props.글제목[0]}</h2>
      <p>날짜</p>
      <p>상세내용</p>
    </div>
  )
}
```

