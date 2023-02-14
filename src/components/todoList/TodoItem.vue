<template>
  <div class="item">
    <div class="item-left">
      <span class="item-left__id">{{ id }}.</span>
      <span class="item-left__text" v-if="!isInput">{{ textEdit }}</span>
      <input class="item-left__input" v-else v-model="textEdit" />
    </div>

    <div class="item-right">
      <img
        class="item-right__button"
        src="@/assets/svg/pencil.svg"
        alt="Edit todo"
        @click="isInput = !isInput"
      />
      <img
        class="item-right__button"
        src="@/assets/svg/trash.svg"
        alt="Delete todo"
        @click="$emit('delete', id - 1)"
      />
    </div>
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

<style lang="scss" scoped>
.item {
  background-color: rgb(219, 211, 211);
  display: flex;
  justify-content: space-between;
  margin: 20px 10px;
  padding: 10px;
  border-radius: 5px;
  &__id {
    padding-right: 10px;
  }
}
.item-wrapper__left {
  text-align: justify;
}
.item-right {
  display: flex;
  gap: 5px;
  &__button {
    border-radius: 5px;
    background-color: red;
    width: 25px;
    height: 25px;
  }
  &__button:first-child {
    background-color: green;
  }
}

.item-left {
  text-align: center;
  display: flex;
  gap: 10px;
  &__input {
    width: 350px;
  }
}
</style>