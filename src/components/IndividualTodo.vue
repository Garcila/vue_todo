<template>
    <li v-bind:id="id">
      <button
        @click="dT"
      >
      Delete
      </button>
      <input
        type="checkbox"
        v-model="checked"
        @click="toggleCompletion"
      >
      <label
        :for="todo"
        v-text="todo"
        :class="{'completed' : checked}"
      >
      </label>
    </li>
</template>

<script>

export default {
  name: 'IndividualTodo',
  props: ['todo', 'id'],
  data () {
    return {
      checked: false
    }
  },
  methods: {
    toggleCompletion () {
      this.checked = !this.checked
    },
    dT (id) {
      this.$emit('deleteTask', id)
    }
  }
}
</script>

<style scoped>
  .completed {
    text-decoration: line-through;
  }

</style>
