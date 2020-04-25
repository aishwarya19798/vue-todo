<template>
  <div id="app">
    <div class="content">
      <Todos v-bind:todos="todosData" v-on:delete-todo="deleteTodo" />
      <AddTodo v-on:add-todo="addTodo" />
    </div>
    <div class="credits">
      Made with <a href="https://vuejs.org">Vue.js</a> by <a href="https://github.com/aishwarya19798/vue-todo">Aishi ❤</a> 
    </div>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
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
      this.todosData = this.todosData.filter((todo) => todo.id !== todoId);
    },
  },
};
</script>

<style>
*{
  box-sizing: border-box;
}
body {
  background-color: rgb(0, 7, 14);
  /* #ffd777,#797979,#424A5D,#68DF; */
  color: aliceblue;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  letter-spacing: 1.5px;
  display: flex;
  justify-content: center;
  margin: 0;
  padding: 0;
}
input {
  background-color: beige;
  border: 0;
  border-radius: 5px;
  padding: 10px;
  font-size: 17px;
  letter-spacing: 1.5px;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
}
a{
  color:#68DF;
  text-decoration: none;
}
</style>

<style scoped>
div {
  max-width: 500px;
  width: 100%;
}
#app{
  display: grid;
  min-height: 90vh;
  align-content: space-between;
}
.credits{
  text-align: center;
  padding:10px 0;
}
.content{
  padding:0 10px;
}
</style>
