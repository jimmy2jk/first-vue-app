<script>
export default{
  props: ["title", "text", "image", "isReversed", "id"]
}
</script>

<template>
  <article class="article" v-show="isReversed" :id="id">
    <div class="image-container">
      <img :src="image" alt="post-image" class="article--photo">
    </div>
    <div class="article--text">
      <h2 class="article--header">{{ title }}</h2>
      <p class="article--content">{{ text }}</p>
    </div>
  </article>

  <article class="article" v-show="!isReversed">
    <div class="article--text">
      <h2 class="article--header">{{ title }}</h2>
      <p class="article--content">{{ text }}</p>
    </div>
    <div class="image-container">
      <img :src="image" alt="post-image" class="article--photo">
    </div>
  </article>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.article {
  display: flex;
  max-height: 400px;
  margin-top: 30px;
  padding: 20px 40px 0px 40px;
  justify-content: space-between;
  font-family: cursive;
  font-weight: 400;
}
.image-container {
  display: flex;
  justify-content: center;
}
.article--photo {
  max-height: inherit;
  border-radius: 10px;
  max-width: 450px;
}

.article--text {
  display: flex;
  flex-direction: column;
  text-align: center;
  width: 600px;
  font-size: 36px;
  margin-left: 20px;
}

.article--text > h2 {
  margin: 0px 0px 30px 0px;
  padding: 0;
  font-weight: 700;
  font-size: 36px;
}

.article--header {
  margin: 0px 0px 20px 0px;
  text-align: center;
}

.article--content {
  margin: 0;
}


</style>