```javascript


document.getElementsByClassName('navbar-toggler')[0].addEventListener('click', function(){
            document.getElementsByClassName('list-group')[0].classList.toggle('show');
        })
```

위에를



밑으로 바꾸면 jQuery가 된다.

```
        // jQuery로 바꾼 형식
        $('navbar-toggler').addEventListener('click', function(){
            document.querySelectorAll('list-group')[0].classList.toggle('show');
        })
```



jQuery 설치는 

jquery cdn 검색해서 

jquery 3.x 의 minified 클릭하고 cdn 가져오기

```
<script src="https://code.jquery.com/jquery-3.6.0.min.js" integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
```

주의할 점은 이 script 밑에서만 jquery 사용 가능하다는 점! 그런데 페이지 로드 성능때문에 body태그 마지막에 넣기는 한다. vscode에서 head태그에 넣은 이유는 온갖곳에서 jquery 쓸거라 여기에 넣음

```
$ 는 제이쿼리의 querySelector
```

```
      <p class="hello">안녕</p>
      <p class="hello">안녕</p>
      <p class="hello">안녕</p>
      <button id="test-btn">버튼</button>

    <script>

        // document.querySelectorAll('.list-group-item')[1]  


        // document.getElementsByClassName('navbar-toggler')[0].addEventListener('click', function(){
        //     document.getElementsByClassName('list-group')[0].classList.toggle('show');
        // })

        // 자바스크립트와 제이쿼리 비교
        // document.querySelector('#test-btn').addEventListener()
        // $('test-btn').on('click', function(){

        // })
        
        $('.hello').css('color', 'red')
        $('.hello').html('헬로우')   // jquery에서는 똑같은거 다 한번에 바꿈
        // $('.hello').addClass('헬로우')
        // $('.hello').removeClass('헬로우')
        // $('.hello').toggleClass('헬로우')
```

