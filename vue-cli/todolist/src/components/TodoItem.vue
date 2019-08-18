<template>
  <li class="item" @click="handelDelete">{{content}}</li>
</template>

<script>
export default {
  props :['content','index'],
  methods :{
    handelDelete (){
      this.$emit('delete',this.index)
    }
  }
}
</script>

<!-- 添加“scoped”属性以仅将CSS限制到此组件 -->
<style scoped>
  .item{
    color: red;
  }
</style>
