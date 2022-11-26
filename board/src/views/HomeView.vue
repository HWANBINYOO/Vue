<template>
<el-row>
  <el-col :span="2"> </el-col>
    <el-col :span="20">
        <el-table :data="articles" style="width: 100%">
            <el-table-column prop="id" label="id" width="80">
            
            </el-table-column>
            <el-table-column prop="userId" label="userId" width="120">
            
            </el-table-column>
            <el-table-column prop="title" label="title"> 

            </el-table-column>
        </el-table>
    </el-col>
</el-row>
</template>

<script>
import apiBoard from '@/api/board';

export default {
  data() {
    return {
      articles : null,
    }
  },
  mounted() {
    // apiBoard.getArticle(1)
    // .then((res) => {
    //   console.log("getArticle" , res);
    // })
    // .catch((e) => console.log(e));
    apiBoard.getArticles(0)
      .then((res) => {
        console.log("getArticles", res);
        this.articles = res.data;
      })
      .catch((e) => console.log(e));

    // apiBoard.postArticle("userId", "title", "body")
    //   .then((res) => {
    //     console.log("postArticle", res);
    //   })
    //   .catch((e) => console.log(e));
  },
}
</script>