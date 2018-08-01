<template>
  <div class="todo">
    <span>{{todo}}</span>
    <button @click="removeTodo" class="remove">Remove</button>
  </div>
</template>

<script>
export default {
  inject: ['emitter'],
  props: {
    todo: {
      type: String,
      required: true,
    },
  },
  methods: {
    removeTodo() {
      this.emitter.$emit('remove', this.todo);
    }
  },
}
</script>

<style>

.todo{
  border-radius: 4px;
  padding: 20px;
  width: 400px;
  margin: 20px auto;
  border: 1px solid grey;

  background-color: azure;

  color: cornflowerblue; 
  display: flex;
  justify-content: space-around;
  
}

.todo span{
  line-height: 31px;
}

.remove{
  background-color: lightcoral;
}
</style>


