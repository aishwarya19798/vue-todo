<template>
    <div>
        <h2>My TodoList</h2>
        <ul>
            <li v-bind:key="todo.id" v-for="todo in todos">
                <Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo',todo.id)"/>
            </li>
        </ul>
    </div>
</template>

<script>
import Todo from './Todo';
export default {
    name : "todos",
    components : {
        Todo
    },
    props : [
        'todos'
    ]
}
</script>

<style scoped>
    div ul li {
        list-style-type: none;
    }
    div ul {
        margin:0;
        padding:0;
    }
    div h2{
        text-decoration: underline;
        text-align: center;
    }
</style>