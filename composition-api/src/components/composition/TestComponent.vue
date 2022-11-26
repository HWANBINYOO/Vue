<template>
<div>
  <h2>{{ username }}</h2>
  <button @click="changeName">ChangeUserName</button>
  <h2>제품명: {{ name }}, 가격 {{ price }}</h2>
  <button @click="changeNameProduct">제품 바꾸기</button>
</div>
</template>

<script>

import { reactive, ref, toRefs } from 'vue';

export default {
  name: 'TestComponent',
  setup(){
    const username = ref("hawnbin");
    function changeName(){
       username.value = "Messi"
    }

    const state = reactive({
      nmae:"TV",
      price:100,
    })

    function changeNameProduct(){
      state.name = "세탁기",
      state.price = 5000;
    }

    return {
      username,
      changeName,
      ...toRefs(state),
      changeNameProduct
    };
  },
};
</script>

<style></style>
