<template>
<div>

  <div class="menu">
    <a v-for="(메뉴,index) in 메뉴들" :key="index">{{메뉴}}</a>
  </div>


  <div>
    <h4 class="red" :style="스타일">{{products[0]}} 원룸</h4>
    <h4>50 만원</h4>
    <button @click="increase(0)">허의매물신고</button> <span>신고수 : {{ 신고수 }}</span>
  </div>
  <div>
    <h4>{{products[1]}} 원룸</h4>
    <h4>70 만원</h4>
    <button @click="increase(1)">허의매물신고</button> <span>신고수 : {{ 신고수 }}</span>
  </div>
  <div>
    <h4>{{products[2]}} 원룸</h4>
    <h4>20 만원</h4>
    <button @click="increase(2)">허의매물신고</button> <span>신고수 : {{ 신고수 }}</span>
  </div>
</div>
</template>

<script>



export default {
  name: 'App',
  data(){
    return {
      신고수 : [0,0,0],
      스타일 : 'color : grey',
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
