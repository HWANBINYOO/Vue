<template>
  <div>
    <h1>h1</h1>
  </div>
</template>

<script>
import apiBoard from '@/api/board';

export default {
  mounted() {
    apiBoard.getArticle(1)
    .then((res) => {
      console.log("getArticle" , res);
    })
    .catch((e) => console.log(e));

    apiBoard.getArticles(0)
      .then((res) => {
        console.log("getArticles", res);
      })
      .catch((e) => console.log(e));

    apiBoard.postArticle("userId", "title", "body")
      .then((res) => {
        console.log("postArticle", res);
      })
      .catch((e) => console.log(e));
  },
}
</script>