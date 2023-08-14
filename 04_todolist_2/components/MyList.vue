<template>
  <ul class="todo-main">
    <MyItem
      v-for="todoObj in todos"
      :key="todoObj.id"
      :todo="todoObj"

    />
  </ul>
</template>

<script>
//test
import pubsub from 'pubsub-js'

import MyItem from "./MyItem.vue";
export default {
  name: "MyList",
  components: { MyItem },
  props: ["todos"],
  mounted(){
    pubsub.subscribe('hello',function(){
      console.log('收到了hello消息');
    })
  }
};
</script>

<style>
/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>