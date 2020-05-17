<template>
  <div class="row">
      <input type="checkbox" @change="toggleComplete" value="todo.isComplete"/>
      <div :class="{isComplete: todo.isComplete}">{{ todo.title }}</div>
      <button @click="removeTodo">Delete</button>
  </div>
</template>

<script>
  export default {
    name: 'TodoItem',
    props: ['todo'],
    methods: {
      toggleComplete(){
        this.$emit('toggle-complete', {...this.$props.todo, isComplete: !this.$props.todo.isComplete});
      },
      removeTodo(){
        if(window.confirm('delete this todo ?')) this.$emit('remove-todo', this.todo.id);
      }
    }
  }
</script>

<style scoped>
    .row {
        display: flex;
        align-items: center;
    }
    .isComplete {
        text-decoration: line-through;
    }
</style>
