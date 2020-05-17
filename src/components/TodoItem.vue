<template>
  <div class="todo">
      <div class="title-area">
          <v-checkbox type="checkbox" @change="toggleComplete" value="todo.isComplete"/>
          <div :class="{isComplete: todo.isComplete}">{{ todo.title }}</div>
      </div>
      <v-btn @click="removeTodo">Delete</v-btn>
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
    .todo {
        display: flex;
        justify-content: space-between;
        align-items: center;
        box-shadow: 0 2px 5px rgba(0,0,0,0.26);
        padding: 16px 6px;
    }
    .todo + .todo {
        margin-top: 5px;
    }
    .title-area {
        display: flex;
        align-items: center;
    }
    .isComplete {
        text-decoration: line-through;
    }
</style>
