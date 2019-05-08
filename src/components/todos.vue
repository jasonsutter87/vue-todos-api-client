<template>
  <section>
    <div class="container-1600">
      <div class="row">
        <div class="col-12">
          <ul class="text-center">
            <li v-for="todo in todos"
              class="todo-listItem">
              {{ todo.title }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>

</template>

<script>
  export default {
    data() {
      return {
        todos: []
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
.form-size{
  height: 50px;
}

.todo-listItem{
  background-color: #fff;
  margin: 1rem 0;
  padding: 1rem 2rem;
  box-shadow: 10px 10px 21px -1px rgba(0,0,0);
}

.todo-listItem:hover{
    text-decoration: line-through;
}

</style>
