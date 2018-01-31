<template>
  <div>
    <input @keyup.enter="addT" type="text" v-model="title" placeholder="Type new todo">
  </div>
</template>

<script>
export default {
  name: 'add-todo',
  data () {
    return {
      title: ''
    }
  },
  methods: {
    addT () {
      this.$emit('addTask', this.title)
      this.title = ''
    }
  }
}
</script>

<style scoped>

</style>
