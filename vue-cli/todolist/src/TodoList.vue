<template>
  <div id="app">
      <div>
            <input class="item" v-model="inputValue"/>
            <button @click="handleSumbit">提交</button>
      </div>
      <ul>
        <todo-item 
        v-for="(item , index) of list"
        :key="index"
        :content="item"
        :index ="index"
        @delete="handelDelete"></todo-item>
      </ul>
  </div>

</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  components : {
    'todo-item' : TodoItem
  },
  data (){
    return {
      inputValue :'',
      list :[]
    }
  },
  methods :{
    handleSumbit (){
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handelDelete (index){
      this.list.splice(index,1)
    }
  }
}
</script>

<style>
  .item{
    color: #000;
  }
</style>
