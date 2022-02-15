# Vue props

- 형제 컴포넌트 간 data 보내기



1. 이벤트 버스 코드 형식

   ```
   //이벤트 버스를 위한 추가 인스턴스 생성
   var eventBus = new Vue();
   
   
   //이벤트를 보내는 컴포넌트
   methods: {
     showLog: function() {
       eventBus.$emit('전달 이벤트명', 전달 데이터);
     }
   }
   
   //이벤트를 받는 컴포넌트
   
   created: function() {
     eventBus.$on('전달받아 트리거된 이벤트명', function(받은 데이터){
       ........
     });
   }
   
   ```

2. 예시

   ```
   <div id="app">
    <child-component></child-component>
   </div>
   
   var eventBus = new Vue();
   
   Vue.component('child-component', {
     template: '<div><button v-on:click="myMethodCall">clickHere</button></div>',
     methods: {
       myMethodCall: function() {
         eventBus.$emit('eventTrigger', '난 너를 호출했다!' ); //이벤트 트리거한쪽(보내는쪽)
       }
     }
   });
   
   var app = new Vue({
     el: '#app',
     created: function() {
       eventBus.$on('eventTrigger', function(value){  //이벤트 받은쪽
         console.log("이벤트를 전달 받은 내용: ", value);
       });
     }
   });
   
   //결과:  난 너를 호출했다!
   ```

   
