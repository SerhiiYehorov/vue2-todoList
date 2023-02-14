<template>
  <div class="list">
    <span class="list__header">My todo list</span>
    <Todoinput class="list__input" @addTodo="addTodo" />
    <List
      class="list__item"
      :items="todos"
      @edit="editTodo"
      @delete="deleteTodo"
    />
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

<style lang="scss" scoped>
.list {
  padding: 20px;
  border-radius: 5px;
  margin: 30px auto;
  padding-bottom: 30px;
  min-width: 400px;
  max-width: 500px;
  background-color: #fff;
  display: flex;
  flex-direction: column;

  &__header {
    padding-top: 30px;
    padding-left: 10px;
    font-weight: 600;
    text-align: left;
  }

  &__input {
    text-align: left;
    margin: 0 10px;
    width: 480px;
  }
  &__iyem {
    margin-bottom: 30px;
  }
}
</style>
