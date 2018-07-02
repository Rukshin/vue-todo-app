<template>
  <div id="app">
    <inputForm @todoWasSubmited="appendTodo"></inputForm>
    <todoList @exterminateChild="exterminate" :items="todoList"></todoList>
  </div>
</template>

<script>
import inputForm from './components/inputForm.vue'
import todoList from './components/todoList.vue'

export default {
  name: 'app',
  components: {
    inputForm,
    todoList
  },
  data() {
      return {
          todoList: []
      }
  },
  methods: {
      appendTodo(todo) {
          this.todoList.push(todo);
      },
      exterminate(key) {
          this.todoList.splice(key, 1);
      }
  },
  created() {
      alert('Mimimi is ilivi');
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
