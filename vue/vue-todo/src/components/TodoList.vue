<template>
    <div>
    <ul>
        <TodoItem
        v-for="todo in todos"
        v-bind:todo="todo"
        v-on:remove-todo="removeTodo"
        />
    </ul>
    </div>
</template>

<script>
  import TodoItem from '@/components/TodoItem'
  export default {
  props: ['todos'],
  components: {
        TodoItem
  },
  methods: {
    removeTodo(id) {
        console.log(id)
        this.todos = this.todos.filter(t=> t.id !==id)
    }
  }
  }
</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>
