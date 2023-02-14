<template>
  <div>
    <span class="todo__id">{{ id }}.</span>
    <span class="todo__item" v-if="!isInput">{{ textEdit }}</span>
    <input v-else v-model="textEdit" />
    <button @click="isInput = !isInput">Edit todo</button>
    <button @click="$emit('delete', id - 1)">Delete todo</button>
  </div>
</template>

<script>
export default {
  props: ["item", "id"],
  data() {
    return {
      isInput: false,
      textEdit: "",
    };
  },

  watch: {
    item: {
      handler(val) {
        this.textEdit = val;
      },
      immediate: true,
      deep: true,
    },
    textEdit: {
      handler() {
        this.$emit("edit", { text: this.textEdit, id: this.id - 1 });
      },
    },
  },
};
</script>

<style scoped>
</style>