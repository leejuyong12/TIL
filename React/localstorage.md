## localstorage



localstorage 문법



자료저장은

```
localStorage.setItem( 'name', 'Kim')
```

자료출력은

```
localStorage.getItem('name')
```

자료삭제는

```
localStorage.removeItem('name')
```



휘발성있는 데이터 저장은 sessionStorage





localStorage에 object 자료를 저장하려면  - 그냥 넣으면 깨짐

```
localStorage.setItem('arr', [1, 2, 3])
> undefined

localStorage.getItem('arr')
> "1, 2, 3"
```

해결방법 - 따옴표쳐서 JSON으로 만들어라 - 혹은 JSON.stringify() 활용하자

```
localStorage.setItem('obj', JSON.stringify({name: 'kim'}))
> undefined

localStorage.getItem('obj')
> "{"name":"kim"}"
```

따옴표를 제거하려면 JSON.parse() 활용하자

```
var a = localStorage.getItem('obj')
> undefined
```

```
JSON.parse(a)
> {name: "kim"}
```

