<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <!-- 子组件 -->
      <Add :addCommen='addCommen'/>
      <List :comments='comments'/>
    </div>
  </div>
</template>
<script>
// 1.引入
import Add from "./comonents/Add.vue";
import List from "./comonents/List.vue";
export default {
  //2.映射成标签
  components: {
    Add,
    List
  },
  data(){
      return{
          comments:[
              {name:'BOB',content:'Vue还不错'},
              {name:'XOX',content:'Vue很强'},
              {name:'LIS',content:'我比较渣'}
          ]
      }
  },
  methods:{
      //添加评论
      addCommen(comment){
          this.comments.unshift(comment)
      }
  }
};
</script>
<style>
</style>
