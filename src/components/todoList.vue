<template>
  <ul class="todoList">
    <TodoItem 
      v-for="(todo, index) in todos" 
      v-bind:todo="todo" 
      v-bind:key="todo.id"
      v-bind:index="index"
      v-bind:delTodo="delTodo"
      v-bind:toggleCompleted="toggleCompleted"
    />
  </ul>
</template>

<script>
  import TodoItem from "@/components/todoItem.vue";

  export default {
    props: ['todos', 'delTodo', 'toggleCompleted'],
    components: {
      TodoItem
    }
  }

</script>

<style scoped>
  .todoList {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>
