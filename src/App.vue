<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <div>
      {{todo.name}}
      </div>
    </div>
    <div>{{message}}</div>
    <message :msg="message"></message>
  </div>
</template>

<script>
import Message from "./components/Message";

export default {
  name: 'App',
  components: {
    Message
  },
  data: () => (
     {
      todos: [
        {id:1, name: 'todo1'},
        {id:2, name: 'todo2'},
        {id:3, name: 'todo3'},
      ],
       message: 'hahaha'
    }
  ),
  // computed: {
  //   messages(){
  //     return this.message + ' babuo'
  //   }
  // },
  // methods: {
  //   m() {
  //     console.log('@@@')
  //     this.message = 'clicked'
  //   }
  // }
}
</script>

<style>
</style>
