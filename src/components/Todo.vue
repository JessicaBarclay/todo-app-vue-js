<template>
  <div class='ui centered card'>
    <div class='content'>
        <div class='header'>
            {{ todo.title }}
        </div>
        <div class='meta'>
            {{ todo.description }}
        </div>
        <span class='right floated trash icon' v-on:click="deleteTodo(todo)">
          delete
        </span>
        <div class='extra content'>
            <span class='right floated edit icon'>
            <i class='edit icon'></i>
          </span>
        </div>
    </div>
</div>
</template>

<script type="text/javascript">
  export default {
    props: ['todo'],
    methods: {
        deleteTodo(todo) {
            this.$emit('delete-todo', todo);
        },
    },
  };
</script>