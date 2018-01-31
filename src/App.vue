<template >
  <div id="app" >
    <Header/>
    <AddTodo @addTask="addTask"/>
    <Todos :todos="todos" @delTask="deleteTask"/>
  </div>
</template>

<script>
import Header from './components/Header'
import AddTodo from './components/AddTodo'
import Todos from './components/Todos'

export default {
  name: 'App',
  components: {
    Header, Todos, AddTodo
  },
  data () {
    return {
      todos: ['Do the laundry', 'Clean the windows at the front', 'GaJ'],
    }
  },
  watch: {
    todos (val) {
      this.$ls.set('todos', val)
    },
    checked (val) {
      this.$ls.set('checked', val)
    }
  },
  created () {
    this.todos = this.$ls.get('todos', [])
    this.checked = this.$ls.get('checked')
  },
  methods: {
    completeTask (e) {
      this.completedTodos.push(e.target.value)
    },
    addTask (e) {
      this.todos.push(e)
    },
    deleteTask (item) {
      this.todos.splice(item.target.parentNode.id, 1)
    }
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
