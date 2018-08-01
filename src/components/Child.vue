<template>
  <div class="wrapper">
    <grand-child></grand-child>
    <ul>
      <li v-for="todo in todos" :key="todo">
        <todo-item :todo="todo"></todo-item>
      </li>
    </ul>

  </div>
</template>

<script>

import GrandChild from './GrandChild.vue';
import TodoItem from './TodoItem.vue'

export default {
  inject: ['state'],
  components: {
    GrandChild,
    TodoItem
  },
  computed: {
    todos(){
      return this.state.todos;
    }
  }
}
</script>

<style scoped>
  li{
    list-style: none;
  }
</style>



