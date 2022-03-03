```javascript
    <div class="alert-box" id="alert">알림창임<button onclick="aboutModal('none')">닫기</button></div>
    <button onclick="aboutModal('block')">버튼</button>

    <script>
        // 1. 이렇게 2개 만들 필요 없이
        // function openModal() {
        //     document.getElementById('alert').style.display='block';
        // }

        // function closeModal() {
        //     document.getElementById('alert').style.display='none';
        // }
        // 1. 이렇게 하나로 만들자, 참고로 구멍 여러개 뚫어서 만들수도 있음 , 그리고 구멍이라 하믄 여기서 파라미터를 말한다.
        function aboutModal(구멍) {
            document.getElementById('alert').style.display = 구멍;
        }
    </script>
```



alert 창 한번에 입력하기

```javascript
    <div class="alert-box" id="alert">
        <p id="title">알림창임</p>
        <button onclick="aboutModal('none');">닫기</button>
    </div>
    <button onclick="aboutModal('block', '아이디입력하기');">아이디열기</button>
    <button onclick="aboutModal('block', '비밀번호입력하기');">비밀번호열기</button>
    <script>
        function aboutModal(구멍, 무엇을) {
            document.getElementById('alert').innerHTML = 무엇을;
            document.getElementById('alert').style.display = 구멍;
        }
    </script>
```

