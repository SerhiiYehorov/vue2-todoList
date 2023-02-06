<template>
  <div>
    <div class="todo" v-for="(item, i) in items" :key="i">
      <span class="todo__id">{{ i + 1 }}.</span>
      <span class="todo__item">{{ item }}</span>
      <button @click="$emit('delete', i)">Delete todo</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["items"],
};
</script>

<style scoped>
.todo__id,
.todo__item {
  padding-right: 5px;
  padding-top: 25px;
}
</style>
