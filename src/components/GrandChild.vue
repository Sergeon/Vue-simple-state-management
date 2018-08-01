<template>
<div class="wrapper">
  <input v-model="value">
  <button @click="emitValue" class="add">Add</button>
</div>
</template>

<script>
export default {
  inject: ['emitter'],
  data() {
    return {
      value: '',
    }
  },
  methods: {
    emitValue(){
      this.emitter.$emit('input', this.value);
      this.value = '';
    }
  }
}
</script>

<style scoped>
.add{
  margin-left: 40px;
}

input{
  height: 32px;
  border-radius: 4px;
  outline: 0;
  border: 1px solid grey;
}
</style>



