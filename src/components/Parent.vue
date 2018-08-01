<template>
  <div class="wrapper">
    <p>Simple state management with provide/inject and event emitters</p>
    <child-component></child-component>
  </div>
</template>

<script>

import ChildComponent from './Child.vue';
import emitter from '../emitter';
export default {
  components: {
    ChildComponent,
  },
  data(){
    return {
      state: {
        todos: [],
      }
    }
  },
  created() {
    this.registerOnInput();
    this.registerOnRemove();
  },
  methods: {
    registerOnInput(){
      emitter.$on('input', todo => {

        if(! todo) return;

        const found = this.state.todos.find(t => t === todo);
        if(found) return;

        this.state.todos.splice(0,0,todo);
      });
    },
    registerOnRemove(){
      emitter.$on('remove', todo => {
        const i = this.state.todos.findIndex(t => t === todo);

        if(i !== -1){
          this.state.todos.splice(i, 1);
        }
      });
    },
  },
  provide() {
    return {
      emitter,
      state: this.state,
    }
  }
}
</script>

<style>

  button{
    background-color: mediumaquamarine;
    color: white;
    padding: 8px 12px;
    border: 1px solid transparent;
    border-radius: 4px;
  }

  button:hover{
    cursor: pointer;
  }

  button:focus{
    outline: 0;
  }

</style>



