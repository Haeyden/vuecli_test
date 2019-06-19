<template>
  <div>
    <div class="col-md-4">
      <form class="form-horizontal">
        <div class="form-group">
          <label>用户名</label>
          <input type="text" class="form-control" placeholder="用户名" v-model="name">
        </div>
        <div class="form-group">
          <label>评论内容</label>
          <textarea class="form-control" rows="6" placeholder="评论内容" v-model="content"></textarea>
        </div>
        <div class="form-group">
          <div class="col-sm-offset-2 col-sm-10">
            <button type="button" class="btn btn-default pull-right" @click="add">提交</button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>
<script>
export default {
    //从父组件接收到的函数可以通过以下两种方式接收
    // props:['addCommen'],
    props:{
        addCommen:{
            type:Function,
            required:true
        }
    },
    data(){
        return{
            name:'',
            content:''
        }
    },
    methods:{
        add(){
            //收集数据 v-model
            //1.检查数据合法性
            const name=this.name.trim()
            const content=this.content.trim()
            if(!name || !content){
                alert('姓名或者内容不能为空')
            }
            //2.根据输入的数据封装为comment对象
            const comment={
                name,
                content
            }
            //3.添加到comments中
            this.addCommen(comment)
            //4.清除输入
            this.name=''
            this.content=''
        }
    }
};
</script>
<style>
</style>
