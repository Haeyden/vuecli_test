<template>
  <div>
    <li class="list-group-item">
      <div class="handle">
        <a href="javascript:;">删除</a>
      </div>
      <p class="user">
        <span>{{comment.name}}</span>
        <span>说:</span>
      </p>
      <p class="centence">{{comment.content}}</p>
    </li>
  </div>
</template>
<script>

export default {
    //声明接收父组件的属性
    props:{
        comment: Object
    }
        // props:['comment']
};
</script>
<style>
li {
  transition: .5s;
  overflow: hidden;
}

.handle {
  width: 40px;
  border: 1px solid #ccc;
  background: #fff;
  position: absolute;
  right: 10px;
  top: 1px;
  text-align: center;
}

.handle a {
  display: block;
  text-decoration: none;
}

.list-group-item .centence {
  padding: 0px 50px;
}

.user {
  font-size: 22px;
}
</style>
