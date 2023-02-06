<template>
  <div>
    <List :items="todos" @delete="deleteTodo" />
    <Todoinput @addTodo="addTodo" />
  </div>
</template>

<script>
import List from "../todoList/List.vue";
import Todoinput from "./Todoinput.vue";

export default {
  components: {
    List,
    Todoinput,
  },
  data() {
    return {
      todos: [],
    };
  },

  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    },

    deleteTodo(i) {
      this.todos.splice(i, 1);
    },
  },
};
</script>

<style></style>
