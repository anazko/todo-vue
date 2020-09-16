<template>
  <div id="app">
    <h1 v-bind:title="message">Todo vue</h1>
    <AddTodo 
      v-bind:addTodo="addTodo"
    />
    <TodoList 
      v-bind:todos="todos" 
      v-bind:delTodo="delTodo"
      v-bind:toggleCompleted="toggleCompleted"
    />
  </div> 
</template>

<script>
import AddTodo from "@/components/addTodo.vue";
import TodoList from "@/components/todoList.vue";

export default {
  name: 'App',
  data: () => ({
    todos: [],
    message: "lol kek!"
  }),
  mounted: function() {
    this.todos = [
      { id: 1, title: "First todo", completed: false },
      { id: 2, title: "Second todo", completed: true },
      { id: 3, title: "Third todo", completed: false },
      { id: 4, title: "Four todo", completed: false },
      { id: 5, title: "One more todo", completed: false }
    ]
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    },
    delTodo(id) {
      this.todos = this.todos.filter(item => id !== item.id);
    },
    toggleCompleted(id) {
      let index = this.todos.findIndex(item => id === item.id);
      this.todos[index].completed = !this.todos[index].completed;
    }
  },
  components: { TodoList, AddTodo }
}
</script>

<style>

  * {
    box-sizing: border-box;
  }

  body {
    background: #555;
  }

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background: #fff;
  margin: 60px auto;
  max-width: 90%;
  padding: 30px;
  border-radius: 3px;
}
</style>
