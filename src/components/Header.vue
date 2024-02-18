<script>
import Nav from './Nav.vue';

export default {
  props: ["logo", "title"],
  components: {
    Nav
  }
}
</script>


<template>
  <header>
    <div class="header">
      <img :src="logo" alt="logo" class="header--logo">
      <h1>{{title}}</h1>
    </div>
    <Nav />
  </header>
</template>


<style scoped>
.header {
  display: flex;
  height: 60px;
  padding: 10px 20px;
  background-color: black;
  color: white;
  background: linear-gradient(
    to right,
    #001f54 7%,
    #034078,
    #1282a2 70%,
    #97d7d7
  );
  color: rgb(25, 197, 128);
  font-family: cursive;
}
.header > h1 {
  margin: 0;
  padding: 4px 30px;
}
</style>