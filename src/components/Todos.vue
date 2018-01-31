<template>
    <ul >
      <IndividualTodo v-for="(todo, i) in todos" :key='todo + i' :todo="todo" :id="i" @deleteTask="delTask"/>
    </ul>
</template>

<script>
import IndividualTodo from './IndividualTodo'

export default {

  name: 'todos',
  props: ['todos'],
  components: {
    IndividualTodo
  },
  methods: {
    delTask (item) {
      this.$emit('delTask', item)
    }
  }
}
</script>

<style scoped>

</style>
