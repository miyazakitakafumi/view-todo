<template>
  <v-container fluid>
    <div class="add-section">
      <v-text-field type="text" v-model="title" />
      <v-btn class="add-btn" @click="addTodo">Add</v-btn>
    </div>
      <todo-item v-for="todo in todos" :key="todo.id" :todo="todo" @toggle-complete="updateComplete" @remove-todo="removeTodo"/>
  </v-container>
</template>

<script>
  import TodoItem from './TodoItem'
  import { v4 as uuidv4 } from 'uuid'

  export default {
    name: 'Todos',
    components: {
      TodoItem
    },
    data() {
      return{
        todos: [
          {id: 1, title: 'todo1', isComplete: false},
          {id: 2, title: 'todo2', isComplete: false},
          {id: 3, title: 'todo3', isComplete: false},
        ],
        title: '',
      }
    },
    methods: {
      updateComplete(newTodo){
        this.todos = this.todos.map(todo => {
          if (todo.id === newTodo.id) return newTodo;
          return todo
        })
      },
      removeTodo(todoId){
        this.todos = this.todos.filter(todo => todo.id !== todoId)
      },
      addTodo(){
        if(this.title === '') return window.alert('Please input todo title');
        this.todos = [...this.todos, {id: uuidv4(), title: this.title, isComplete:false}];
        this.title = ''
      }
    }
  }
</script>

<style scoped>
  .add-section {
    display: flex;
    align-items: center;
  }
  .add-btn {
    margin-left: 10px;
  }
</style>
