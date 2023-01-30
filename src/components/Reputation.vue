<template>
  <section class="reputation">
    <h4>Our Reputation</h4>
    <div class="reputation__cards">
      <ReputationCard
        v-for="item in cards"
        :key="item.header"
        :header="item.header"
        :text="item.text"
      />
    </div>
  </section>
</template>

<script>
import ReputationCard from "./ReputationCard.vue";

export default {
  name: "Reputation",
  components: {
    ReputationCard,
  },
  props: ["cards"],
};
</script>

<style>
.reputation__cards {
  display: flex;
  justify-content: flex-end;
  gap: 20px;
}
</style>