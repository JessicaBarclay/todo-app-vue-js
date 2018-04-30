<template>
  <div>
    <h1>Todos</h1>
      <todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo"></todo>
  </div>
</template>

<script>
import Todo from './Todo';
export default {
    components: {
      Todo,
    },  
    name: 'TodoList',
    props: ['todos'],
    methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
  },
};
</script>