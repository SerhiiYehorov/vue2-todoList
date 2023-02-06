<template>
  <div>
    <input v-model="todo" type="text" placeholder="input your todo" />
    <button @click="addTodo">Add todo</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: "",
    };
  },
  methods: {
    addTodo() {
      if (!this.todo) {
        return;
      }
      this.$emit("addTodo", this.todo);
      this.todo = "";
    },
  },
};
</script>

<style></style>
