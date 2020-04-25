<template>
    <div v-bind:class="{ 'completed' : todo.completed }" >
        <p v-on:click="markcomplete">{{todo.title}}</p>
        <button @click="$emit('delete-todo', todo.id)">Delete</button>
    </div>
</template>

<script>
export default {
    name : 'todo',
    props : [
        "todo"
    ],
    methods : {
        markcomplete() {
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
    .completed {
        text-decoration : line-through;
    }

</style>