<template lang="html">
  <div class="">
    <div v-for="todo in todos" :key="todo.id" class="">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
}
</script>

<style lang="css" scoped>
</style>
