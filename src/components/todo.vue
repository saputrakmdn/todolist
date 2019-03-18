<template>
  <div class="app">
    <div class="container">
      <div class="row header">
        <h1 class="center-align teal-text">To-Do List!</h1>
      </div>
      <div class="row">
        <form @submit.prevent="submitTodo">
          <div class="input-field">
            <i class="material-icons prefix">list</i>
            <textarea v-model="newTodo" id="icon_prefix2" class="materialize-textarea"></textarea>
            <label for="icon_prefix2">What to do?</label>
          </div>
          <button class="btn waves-effect col s12">Tambah</button>
        </form>
      </div>
      <div class="row">
       <table class="table" v-if="todos.length > 0">
            <thead>
                <tr>
                    <th scope="col">#</th>
                    <th scope="col">Todo</th>
                    <th scope="col">Action</th>
                </tr>
            </thead>
            <tbody v-for="(todo, index) in todos" :key="index">
                <td scope="row">{{index}}</td>
                <td>{{todo}}</td>
                
                <td>
                    <button class="btn btn-danger" @click="deleteTodo(index)">Delete</button></td>
            </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'todo',
  data() {
    return {
      todos: [{}],
      newTodo: '',
    
    };
  },
  watch: {
    todos: {
      handler() {
        localStorage.todos = JSON.stringify(this.todos);
      },
      deep: true,
    },
  },
  mounted() {
    if (localStorage.todos) {
      this.todos = JSON.parse(localStorage.todos);
    }
  },
  methods: {
    submitTodo() {
      this.todos.push(
        this.newTodo
      )
      this.newTodo = '';
    },
    deleteTodo(index) {
                    this.todos.splice(index, 1);
                },

  },
 
  

};
</script>

<style lang="scss">
.header{
  margin-top: 100px;
}
</style>
