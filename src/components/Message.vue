<template>
  <div>
    {{message}}
    <button @click="updateMessage">change</button>
  </div>
</template>

<script>
export default {
  name: 'Message',
  props: {
    msg: String
  },
  data(){
    return {
      message: this.$props.msg
    }
  },
  methods: {
    updateMessage(){
      this.message = 'kkk'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
