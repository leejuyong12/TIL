### input 이벤트

<input>에 입력될 때마다 발생

```javascript
<script>
 
      document.getElementById('email').addEventListener('change', function() {
        console.log('안녕')
      })
      
 </script>
```





### change 이벤트

<input>에 입력한 값이 바뀌고 포커스를 잃을 때 발생

```javascript
<script>
 
      document.getElementById('email').addEventListener('change', function() {
        console.log('안녕')
      })
      
 </script>
```



### 조건 2개 이상을 동시에 비교하고 싶다면 && 그리고 || 연산자

and 조건

```
<script>
 
      if (1 == 1 && 2 == 2){
      		console.log('안녕')
      }
      
 </script>
```

or 조건

```
<script>
 
      if (1 == 1 || 2 == 2){
      		console.log('안녕')
      }
      
 </script>
```

