<template>
<div>

  <div class="black-bg" v-if="모달창state == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창state = false">x</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(메뉴,index) in 메뉴들" :key="index">{{메뉴}}</a>
  </div>


  <div v-for="(item,index) in roomData" :key="index">
    <img :src="item.image" alt="최" class="room-img">
    <h4>{{item.title}} 원룸</h4>
    <p>{{item.price}}원</p>
  </div>

  <!-- <div>
    <img :src="roomData[0].image" alt="최" class="room-img">
    <h4>{{roomData[0].title}} 원룸</h4>
    <p>{{roomData[0].price}}원</p>
  </div> -->

 
</div>
</template>

<script>

import roomData from './data/rooms.js'

export default {
  name: 'App',
  data(){
    return {
      roomData,
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
  width:100%;
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