<script>
export default {
  data() {
    return {
      message: "",
    };
  },
  methods: {
    showMessage(buttonName) {
      this.message = buttonName;
    },
    hide() {
      this.message = "";
    }
  },
};
</script>

<template>
  <div class="buttons">
    <div class="three-buttons">
      <button @click="showMessage('Button 1')">Button 1</button>
      <button @click="showMessage('Button 2')">Button 2</button>
      <button @click="showMessage('Button 3')">Button 3</button>
      <button @click="hide()">Hide</button>
    </div>
    <div class="message">
      <p>{{ message }}</p>
    </div>
  </div>
</template>

<style scoped>
.buttons {
  display: flex;
  flex-direction: column;
  height: 150px;
  margin-top: 30px;
  padding: 0px 40px;
}
.three-buttons {
  display: flex;
  justify-content: space-evenly;
}

.three-buttons > button {
  height: 50px;
  width: 100px;
  border-radius: 10px;
  background-color: aliceblue;
  border: 3px solid rgb(3, 3, 82);
  color: rgb(3, 3, 82);
  font-family: cursive;
  font-size: 18px;
  font-weight: 700;
}
.message {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: cursive;
  font-size: 36px;
  color:aliceblue;
  height: 100%;
}

.message > p {
  margin: 0;
  padding: 0;
}

</style>