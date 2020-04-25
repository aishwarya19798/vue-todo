<template>
  <div v-bind:class="{ completed: todo.completed }">
    <p v-if="!editingMode" v-on:click="markcomplete">{{ todo.title }}</p>
    <input v-else v-model="todo.title" />
    <div>
      <button @click="edit"><img src="/assets/pencil.svg" /></button>
      <button @click="$emit('delete-todo', todo.id)">
        <img src="/assets/bin.svg" alt="" srcset="" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "todo",
  props: ["todo"],
  data() {
    return {
      editingMode: false,
    };
  },
  methods: {
    markcomplete() {
      this.todo.completed = !this.todo.completed;
    },
    edit() {
      this.editingMode = !this.editingMode;
    },
  },
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
  color:grey;
}
div {
  display: flex;
  justify-content: space-between;
  padding:5px 0;
}
div p{
    font-size: 17px;
}
div button {
  border: 1px solid transparent;
  border-radius: 50px;
  background-color: transparent;
}
</style>
