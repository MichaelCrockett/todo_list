<template lang="html">
  <div class="">
    <form @submit="addTodo">
      <input type="text" name="title" placeholder="Add Stuff to Get Done" v-model="title">
      <input type="submit" name="" value="submit" class="btn">
    </form>
  </div>
</template>

<script>
// import { v4 as uuidv4 } from 'uuid';
export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      }
      //send up to parent
      this.$emit('add-todo', newTodo);

      this.title = '';
    }
  }
}
</script>

<style lang="css" scoped>
  form {
    display: flex;
  }

  input[type="text"] {
    flex: 10;
    padding: 5px;
  }

  input[type="submit"] {
    flex: 2;
  }
</style>
