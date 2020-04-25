<template>
    <div>
        <form @submit="addTodo">
           <input type="text" name="title" v-model="title">
           <button type="submit"><img src="/assets/pencil.svg"></button>
        </form>
    </div>
</template>

<script>
import {uuid} from 'vue-uuid';

export default {
    name : 'AddTodo',
    data() {
        return {
            title : ''
        }
    },
    methods : {
        addTodo(e) {
            e.preventDefault();
            const newTodoObj = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodoObj);
            this.title = '';
        }
    }
}
</script>

<style scoped>
    div{
        padding-top:15px;
    }
    div form{
        display: flex;
        justify-content: space-between;
        align-content: center;
    }
    div form input{
        width:100%;
        border:0;
        border-radius: 5px;
    }
    div button {
        border:1px solid transparent;
        background-color: transparent;
    }
</style>