<template>
<div>

  <div class="menu">
    <a v-for="(메뉴,index) in 메뉴들" :key="index">{{메뉴}}</a>
  </div>

  <div v-for="(룸,index) in 룸들" :key="index">
      <h4>{{룸}}</h4>
      <h4>{{(index+20) * 2}}만원</h4>
  </div>
</div>
</template>

<script>



export default {
  name: 'App',
  data(){
    return {
      스타일 : 'color : blue',
      메뉴들 : ['Home' , 'Shop' , 'About'],
      룸들 : ['역삼동원룸' , '천호동원룸' , '마포구원룸'],
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
