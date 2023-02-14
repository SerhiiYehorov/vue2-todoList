<template>
  <div>
    <h4>My todo list</h4>
    <List :items="todos" @edit="editTodo" @delete="deleteTodo" />
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

    editTodo(todo) {
      this.todos.splice(todo.id, 1, todo.text);
    },
  },
};
</script>

<style></style>
