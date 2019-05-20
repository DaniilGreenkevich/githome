<template>
        <li>
             <span v-bind:class="{done: todo.completed}">
                <input type='checkbox'
                v-on:change="todo.completed = !todo.completed">
                <strong>{{ todo.id }} </strong>
                 {{ todo.title }}
             </span>
             <button class="rm"
                v-on:click="$emit('remove-todo', todo.id)"
             >&times;</button>
        </li>
</template>

<script>
 export default {
   props: {
    todo: {
     type: Object,
     requited: true
    }
   }
 }
</script>

<style scoped>
    li {
        border: 1px solid #c4c4c4;
        display: flex;
        justify-content: space-between;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
    }

    .rm {
        background: red;
        border-radius: 50%;
        color: #fff;
        font-weight: bold;
    }
    .done {
        text-decoration: line-through;
    }
    input {
        margin-right: 1rem;
    }

</style>