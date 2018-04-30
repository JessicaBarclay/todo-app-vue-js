<template>
  <div id="app">
    <router-view/>
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create-todo="addTodo"></create-todo>
  </div>
</template>

<script>
  import TodoList from './components/TodoList'
  import CreateTodo from './components/CreateTodo'

  export default {
    components: {
      TodoList,
      CreateTodo,
    },
    methods: {
      addTodo(newTodo) {
        this.todos.push(
          newTodo
        );
      },
    },
    name: 'App',
      data() {
      return {
        todos: [{
          title: 'Eat cake',
          description: 'yum yum',
        }],
      };
    },
  };
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
