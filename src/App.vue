<template>
  <div id="app">
    <Todos v-bind:todos="todosData" v-on:delete-todo="deleteTodo" />
    <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from './components/AddTodo';
export default {
  name: "App",
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todosData: [
        {
          id: 1,
          title: "Go workout",
          completed: false,
        },
        {
          id: 2,
          title: "Do laundry",
          completed: false,
        },
        {
          id: 3,
          title: "Cook food",
          completed: false,
        },
        {
          id: 4,
          title: "Clean up room",
          completed: false,
        },
        {
          id: 5,
          title: "Finish work",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo(newTodoObj) {
      this.todosData.push(newTodoObj);
    },
    deleteTodo(todoId) {
      this.todosData = this.todosData.filter(todo => todo.id !== todoId);
    }
  }
};
</script>

<style></style>
