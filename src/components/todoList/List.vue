<template>
  <div>
    <div class="todo" v-for="(item, i) in items" :key="i">
      <TodoItem
        :id="i + 1"
        :item="item"
        @delete="$emit('delete', $event)"
        @edit="sendEdit"
      />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  components: {
    TodoItem,
  },

  props: ["items"],

  methods: {
    sendEdit(item) {
      const params = {
        text: item.text,
        id: item.id,
      };

      this.$emit("edit", params);
    },
  },
};
</script>

<style scoped>
.todo__id,
.todo__item {
  padding-right: 5px;
  padding-top: 25px;
}
</style>
