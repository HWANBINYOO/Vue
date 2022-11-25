<template>
<div>

  <div class="black-bg" v-if="모달창state == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <div @click="모달창state = false">x</div>
    </div>
  </div>

  <div class="menu">
    <a v-for="(메뉴,index) in 메뉴들" :key="index">{{메뉴}}</a>
  </div>

  <div>
    <img src="./assets/캡.jpg" alt="최" class="room-img">
    <h4 class="red" :style="스타일" @click="모달창state = true">{{products[0]}} 원룸</h4>
    <h4>50 만원</h4>
    <button @click="increase(0)">허의매물신고</button> <span>신고수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <img src="./assets/캡.jpg" alt="준" class="room-img">
    <h4>{{products[1]}} 원룸</h4>
    <h4>70 만원</h4>
    <button @click="increase(1)">허의매물신고</button> <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <img src="./assets/캡.jpg" alt="." class="room-img">
    <h4>{{products[2]}} 원룸</h4>
    <h4>20 만원</h4>
    <button @click="increase(2)">허의매물신고</button> <span>신고수 : {{ 신고수[2] }}</span>
  </div>
</div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      모달창state : false,
      신고수 : [0,0,0],
      메뉴들 : ['Home' , 'Shop' , 'About'],
      products : ['역삼동원룸' , '천호동원룸' , '마포구원룸'],
    }
  },
  methods: {
    increase(n){
      this.신고수[n] += 1;
    }
  },

  components: {
  }
}
</script>

<style>
body {margin:0; padding:0}
div{box-sizing: border-box}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img{
  width:20%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

</style>