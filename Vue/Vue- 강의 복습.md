# Vue - 강의 복습

App.vue

```
<template>

  <Discount v-if="showDiscount == true" />
  <p>지금 결제하면 {{amount}}% 할인</p>


  <button @click="priceSort">가격순정렬</button>
  <button @click="sortBack">되돌리기</button>
  <button @click="reversepriceSort">가격역순정렬</button>



  <div class="start" :class="{ end : 모달창열렸니 }"> -->
    <!-- 뒤에꺼는 조건부 적용 -->
    <Modal @closeModal="모달창열렸니 = false;" :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>
  </div>
  <!-- <transition name="fade">
    <Modal @closeModal="모달창열렸니 = false;" :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>
  </transition> -->

  <!-- props 보내기 -->
  <!-- 자식 :데이터="데이터"   Modal은 자식, App은 부모 -->
  <!-- : 는 v-bind: 랑 똑같다 -->

  <div class="menu">
    <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
  </div>

  <Card @openModal="모달창열렸니 = true; 누른거 = $event" :원룸="원룸들[i]" v-for="(작명, i) in 원룸들" :key="i"/>
  <!-- $event 는 자식이 보낸 데이터 담아놓은 것 -->
  <!-- openModal은 자식Modal이 보낸거 받는 거다 -->
  <!-- <Card :원룸="원룸들[1]" />
  <Card :원룸="원룸들[2]" />
  <Card :원룸="원룸들[3]" />
  <Card :원룸="원룸들[4]" />
  <Card :원룸="원룸들[5]" /> -->



  <!-- <div v-for="(a,i) in 원룸들" :key="i">
    <img :src="a.image" class="room-img">  
    <h4 @click="모달창열렸니 = true; 누른거 = i">{{a.title}}</h4>
    <p>{{a.price}}원</p>
  </div> -->
  <!-- HTML 태그 안의 속성 데이터바인딩은 :어쩌구   , HTML 태그 안의 내용 데이터바인딩은 {{어쩌구}} -->

  <!-- <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{products[1]}}</h4>
    <p>50만원</p>
    <button @click="신고수[1]++">허위매물신고</button>
    <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <h4>{{products[2]}}</h4>
    <p>50만원</p>
    <button @click="신고수[2]++">허위매물신고</button>
    <span>신고수 : {{ 신고수[2] }}</span>
  </div> -->
</template>

<script>
import data from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';
 
export default {
  name: 'App',
  data(){
    return {
      amount: 30,
      showDiscount : true,
      원룸들오리지널 : [...data],  // 원본 원룸들  [...] 쓰면 별개의 사본을 만들어준다(다른거 바꿔도 영향 안옴)
      오브젝트 : { name : 'kim', age : 20},
      누른거: 0,
      원룸들: data,  // 정렬할때 쓰는 원룸들
      모달창열렸니 : false,
      신고수 : [0, 0, 0],
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'] //데이터를 부모에서도 쓰는거면 자식에서 만들지 말고 부모에서 만들자(그냥 해라)
    }
  },
  methods : {
    increase(){
      this.신고수 += 1;
    },
    priceSort(){
      this.원룸들.sort(function(a,b){
        return a.price - b.price
      })  // a - b 가 음수면 a를 왼쪽으로 보내주세요 // sort 는 원본을 변형시킴
    },
    reversepriceSort(){
      this.원룸들.sort(function(a,b){
        return b.price - a.price
      })
    },
    sortBack(){
      this.원룸들 = [...this.원룸들오리지널]; // 이건 값을 공유해주세요
    }
  },
  beforeUpdate(){
    if (this.month == 2){
      alert('2개월은 너무 적소')
    }
  },
  mounted(){
    setInterval(()=>{
      this.amount--;
    }, 1000);
  },
  components: {
    Discount,
    Modal,
    Card,
  }
}
</script>

<style>


.room-img {
  width: 100%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background : darkslateblue;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color : white;
  padding : 10px;
}

.start {
  opacity: 0;
  transition: all 1s;
}
.end {
  opacity: 1;
}
/* 퇴장 애니메이션 */
/* 시작 스타일 */
.fade-leave-from {
  opacity: 1;

}
/* transition */
.fade-leave-active {
  transition: all 1s;

}
/* 끝날때 스타일 */
.fade-leave-to {
  opacity: 0;

}
/* 시작시 스타일 */
.fade-enter-from {
  opacity: 0;
} 
/* transition시 스타일 */
.fade-enter-active {
  transition: all 1s;
}
/* 끝날시 스타일 */
.fade-enter-to {
  opacity: 1;
}

.fade-enter-from {
  transform: translateY(-1000px);
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  transform: translateY(0px);
}


body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 
</style>

```



Card.vue

```
<template>
  <!-- 원름 6개를 한번에 다 컴포넌트로 하려면 여기에 반복문, 여기에 반복문 안해도 된다.(취향차이) -->
  <div>
    <img :src="원룸.image" class="room-img">  
    <h4 @click="send">{{ 원룸.title }}</h4>
    <!-- <h4 @click="$emit('openModal', 원룸.id )">{{ 원룸.title }}</h4> -->

    <!-- props로 보낸 데이터는 수정 금지 (Read only) 그래서  custom event 활용해보자   $emit('작명하기') 은 데이터 보내는것-->
    <p>{{원룸.price}}원</p>
  </div>
</template>

<script>
export default {
    name: "Card",
    props: {
        원룸: Object,
        // 모달창열렸니: Boolean
    },
    methods: {
        send() {
            this.$emit('openModal', this.원룸.id )
        }
    }
}
</script>

<style>

</style>
```





Modal.vue

```
<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" alt="">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      
      <input v-model="month">
      <!-- data 에 month : 1이라고 해도 문자형으로 저장됨. 무조건 숫자로 받게 하려면 v-model.number 이렇게 하자 -->
      <!-- <input @input="month = $event.target.value"> -->

      <input type="range">

      <!-- $event.target.value는 사용자가 입력한 값 -->
      <!-- @click 은 클릭했을때, @change 는 입력하고 다른데 커서 찍으면 @input은 입력이 바뀔때마다-->
      <p>{{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }}원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Modal',
    data(){
        return {
            month: 1,
        }
    },
    watch : {
        month(a){
            if (a >= 13) {
                alert('13이상 입력하지 마셈')
            } else if (isNaN(a) == true) {
                alert('글자 입력하지 마셈');
                this.month = 1;
            }
        } // watch는 데이터 감시  watch : { 감시할 데이터(){}}
    },
    props: {
        원룸들 : Array,
        누른거 : Number,
        모달창열렸니 : Boolean,
    }
}
</script>

<style>

</style>
```



Discount.vue

```
<template>
    <div class="discount">
    <h4>지금 결제하면 30% 할인</h4>
  </div>
</template>

<script>
export default {
  name: 'Discount',

}
</script>

<style>
.discount {
    background: #eee;
    padding: 10px;
    margin: 10px;
    border-radius: 5px;
}
</style>
```



oneroom.js

```
export default [{
    id : 0,
    title: "Sinrim station 30 meters away",
    image: "https://codingapple1.github.io/vue/room0.jpg",
    content: "18년 신축공사한 남향 원룸 ☀️, 공기청정기 제공",
    price: 340000
    },
    {
    id : 1,
    title: "Changdong Aurora Bedroom(Queen-size)",
    image: "https://codingapple1.github.io/vue/room1.jpg",
    content: "침실만 따로 있는 공용 셰어하우스입니다. 최대 2인 가능",
    price: 450000
    },
    {
    id : 2,
    title: "Geumsan Apartment Flat",
    image: "https://codingapple1.github.io/vue/room2.jpg",
    content: "금산오거리 역세권 아파트입니다. 애완동물 불가능 ?",
    price: 780000
    },
    {
    id : 3,
    title: "Double styled beds Studio Apt",
    image: "https://codingapple1.github.io/vue/room3.jpg",
    content: "무암동인근 2인용 원룸입니다. 전세 전환가능",
    price: 550000
    },
    {
    id : 4,
    title: "MyeongIl Apartment flat",
    image: "https://codingapple1.github.io/vue/room4.jpg",
    content: "탄천동 아파트 월세, 남향, 역 5분거리, 허위매물아님",
    price: 680000
    },
    {
    id : 5,
    title: "Banziha One Room",
    image: "https://codingapple1.github.io/vue/room5.jpg",
    content: "반지하 원룸입니다. 비올 때 물가끔 새는거 빼면 좋아요",
    price: 370000
  }];
```

