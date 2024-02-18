<template>
  <div class="user-form">
    <form @submit.prevent="submitReview">
      <label>
        <input type="checkbox" v-model="isRegistered" class="checkbox" />
        Зареєстрований користувач
      </label>

      <label>
        Ім'я:
        <input v-model="userName" type="text" :disabled="isRegistered" />
      </label>

      <label v-if="!isRegistered">
        Електронна адреса:
        <input v-model="userEmail" type="email" />
      </label>

      <label>
        Відгук:
        <textarea v-model="reviewText"></textarea>
      </label>

      <label>
        Оцінка:
        <select v-model="rating">
          <option v-for="(item, index) in marksList" :value="index + 1">
            {{ item }}
          </option>
        </select>
      </label>

      <div class="buttons">
        <button class="button" type="button" @click="clearForm">
          Очистити
        </button>
        <button class="button" type="submit">Відправити</button>
      </div>
    </form>

    <div v-if="showMessage">
      <p v-if="rating >= 3">Дякуємо за позитивний відгук!</p>
      <p v-else-if="rating >= 2">Ми врахуємо ваші зауваження.</p>
      <p v-else>
        Вибачте, що ви не задоволені. Ми спробуємо виправити ситуацію.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isRegistered: false,
      userName: "",
      userEmail: "",
      reviewText: "",
      rating: 1,
      showMessage: false,
      marksList: ["Погано", "Середньо", "Гарно"],
    };
  },
  methods: {
    submitReview() {
      this.showMessage = true;
    },
    clearForm() {
      this.userName = "";
      this.userEmail = "";
      this.reviewText = "";
      this.rating = 1;
      this.showMessage = false;
    },
  },
};
</script>

<style scoped>
.user-form {
  font-family: "Arial", sans-serif;
  margin: 30px 0px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

form {
  display: flex;
  flex-direction: column;
  background-color: aliceblue;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  max-width: 400px;
  width: 100%;
  color: rgb(3, 3, 82);
  border: 5px solid rgb(3, 3, 82);
}

.checkbox {
  width: 20px;
  height: 20px;
}
.response {
  display: flex;
  flex-direction: column;
  margin-left: 30px;
  right: 10px;
  font-family: cursive;
  font-size: 20px;
  font-weight: 700;
}

label {
  display: block;
  margin-bottom: 8px;
  font-size: 18px;
  font-weight: 700;
}

input,
textarea {
  width: 100%;
  height: 50px;
  padding: 5px 10px;
  margin-bottom: 16px;
  box-sizing: border-box;
  border: 1px solid aliceblue;
  border-radius: 4px;
  background-color: rgb(3, 3, 82);
  font-size: 18px;
}

textarea {
  height: 150px;
}

.button {
  width: 200px;
  background-color: rgb(164, 206, 243);
  color: rgb(3, 3, 82);
  padding: 10px;
  border: 2px solid rgb(3, 3, 82);
  border-radius: 10px;
  cursor: pointer;
  font-family: cursive;
  font-size: 18px;
  font-weight: 700;
  place-self: center;
}

.button:hover {
  background-color: #0056b3;
}

h2 {
  margin-top: 20px;
}

p {
  margin: 8px 0;
}

option,
select {
  background-color: rgb(3, 3, 82);
  border: none;
  font-size: 16px;
}

select {
  height: 30px;
}
</style>
