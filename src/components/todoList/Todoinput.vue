<template>
  <div class="input">
    <input
      class="input__input"
      v-model="todo"
      type="text"
      placeholder="input your todo"
    />
    <img
      src="@/assets/svg/red-cross.svg"
      alt="add todo"
      class="input__button"
      @click="addTodo"
    />
    <!-- <button class="input__button" @click="addTodo">Add todo</button> -->
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

<style lang="scss" scoped>
.input {
  padding-top: 30px;
  display: flex;
  width: 100%;
  justify-items: space-between;

  &__input {
    width: 500px;
    border-radius: 3px;
    border-color: rgb(219, 211, 211);
  }

  &__button {
    background-color: violet;
    border-radius: 3px;
    height: 25px;
    width: 25px;
    margin-left: 10px;
  }
}
</style>
