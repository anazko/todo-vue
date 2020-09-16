<template>
  <li class="todoItem">
    <span v-bind:class="{completed: todo.completed}" >
      <input 
        type="checkbox" 
        v-bind:checked="todo.completed"
        v-on:change="toggleCompleted(todo.id)"
      />
      {{ index }}: {{ todo.title }}
    </span>
    <button class="deleteTodo" v-on:click="delTodo(todo.id)">&times;</button>
  </li>
</template>

<script>
export default {
  props: ['todo', 'index', 'delTodo', 'toggleCompleted'],
  methods: {
  }
}

</script>

<style scoped>

  input {
    margin-right: 1rem;
  }

  .todoItem {
    display: block;
    padding: .5rem;
    border: 1px solid #eee;
    margin-bottom: .3rem;
    display: flex;
    justify-content: space-between;
  }

  .todoItem:hover {
    background: #fafafa;
  }

  .completed {
    text-decoration: line-through;
  }

  .deleteTodo {
    border: none;
    background: transparent;
    font-size: 32px;
    color: red;
    width: 20px;
    height: 20px;
    line-height: 20px;
    text-align: center;
    padding: 0;
    cursor: pointer;
  }

</style>
