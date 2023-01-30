<template>
  <div class="card">
    <h5 class="header">{{ header }}</h5>
    <h6 class="article">{{ text }}</h6>
  </div>
</template>

<script>
export default {
  name: "ReputationCard",

  props: ["header", "text"],
};
</script>

<style scoped>
.card {
  margin: 0;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px 20px 40px;
  gap: 18px;
  border: 1.4px solid #e0e3eb;
  border-radius: 4px;
}

.header {
  margin: 0;
  text-align: start;
  font-weight: 700;
  font-size: 20px;
  line-height: 23px;
  color: #3d445c;
}

.article {
  width: 254px;
  height: 38px;
  margin: 0;
  text-align: start;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #858ead;
}
</style>