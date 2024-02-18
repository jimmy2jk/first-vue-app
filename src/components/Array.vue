<script>
export default {
  props: ["array"],
}
</script>

<template>
  <div class="array">
    <div v-for="(number, index) in array" class="array-element" :key="index">{{ index }}: {{ number }}</div>
  </div>
</template>

<style scoped>
.array {
  display: flex;
  flex-direction: column;
  margin-top: 30px;
  padding: 0px 40px;
  align-items: center;
}

.array-element {
  display: flex;
  width: 100px;
  font-family: cursive;
  font-size: 24px;
  color:aliceblue;
}
</style>