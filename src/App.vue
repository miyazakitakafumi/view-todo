<template>
  <div>
    <todos />
  </div>
</template>

<script>
import Todos from './components/Todos'

export default {
  name: 'App',
  components: {
    Todos,
  },
  data() {
    return{
      todos: [
        {id: 1, title: 'todo1', isComplete: true},
        {id: 2, title: 'todo2', isComplete: false},
        {id: 3, title: 'todo3', isComplete: false},
      ],
    }
  },
  computed: {
  },
  methods: {
  }
}
</script>

<style scoped>
</style>
