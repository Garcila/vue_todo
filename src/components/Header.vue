<template>
  <div class="header">
    <h1 >{{ name }}'s {{title}}'s</h1>
    <h2>{{ subTitle }}</h2>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      title: 'ToDo',
      subTitle: 'getting things done',
      name: 'German'
    }
  }
}
</script>

<style scoped>
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
</style>
