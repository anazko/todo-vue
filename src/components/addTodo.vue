<template>
  <form v-on:submit.prevent="submitHandler">
    <input type="text" v-model="todoText" />
    <input type="submit" value="add" />
  </form>
</template>

<script>
export default {
  data: function() {
    return {
      todoText: ''
    }
  },
  methods: {
    submitHandler() {
      let newTodo = {
        id: Date.now(),
        title: this.todoText,
        completed: false
      }
      this.todoText = '';
      this.addTodo(newTodo);
    }
  },
  props: ['addTodo']
}
</script>

<style scoped>
  form {
    margin: 20px 0;
  }
  input {
    padding: 5px;
  }
</style>