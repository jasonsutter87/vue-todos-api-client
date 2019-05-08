<template>
  <ul>
    <li v-for="todo in todos">{{ todo.title }}</li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      todos: ['taco']
    }
  },
  mounted(){
    fetch('https://vue-todos-api-server.herokuapp.com/todos')
      .then(response => response.json())
      .then((data) => {
        this.todos = data;
      })

  }
}







</script>

<style scoped>

</style>
