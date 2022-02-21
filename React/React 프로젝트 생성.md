# 프로젝트 생성하기

node.js 설치하기 + vscode 설치하기



프로젝트 생성하기

```
npx create-react-app 프로젝트명
npm start
```



state

자주 바뀌고 중요한 데이터는 변수 말고 state로 저장해서 쓰자(바뀔때마다 변경 된거 보여줄 수 있게)

```
let [글제목, 글제목변경] = useState(['남자 코트 추천', '강남 우동 맛집'])
```

