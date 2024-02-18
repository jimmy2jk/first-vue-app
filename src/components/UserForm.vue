<template>
  <div class="user-form">
    <form @submit.prevent="calculateAge">
      <div class="main-fie">
        <label for="name">Ім'я:</label>
        <input v-model="userData.name" type="text" id="name" required />

        <label for="birthDate">Дата народження:</label>
        <input
          v-model="userData.birthDate"
          type="date"
          id="birthDate"
          required
        />
      </div>
      <button type="submit" class="button">Розрахувати вік</button>
    </form>

    <div v-show="showResult" class="response">
      <h2>Результати:</h2>
      <p>Ім'я: {{ userData.name }}</p>
      <p>Дата народження: {{ userData.birthDate }}</p>
      <p>Вік: {{ userAge }}</p>
      <p>Статус: {{ userStatus }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userData: {
        name: "",
        birthDate: "",
      },
      userAge: null,
      userStatus: "",
      showResult: false,
    };
  },
  methods: {
    calculateAge() {
      const birthDate = new Date(this.userData.birthDate);
      const today = new Date();
      const age = today.getFullYear() - birthDate.getFullYear();

      this.userAge = age;
      this.setUserStatus(age);
      this.showResult = true;
    },
    setUserStatus(age) {
      if (age < 6) {
        this.userStatus = "Дитина";
      } else if (age < 18) {
        this.userStatus = "Школяр";
      } else if (age < 25) {
        this.userStatus = "Студент";
      } else {
        this.userStatus = "Дорослий";
      }
    },
  },
};
</script>

<style scoped>
.user-form {
  font-family: "Arial", sans-serif;
  margin: 30px 0px;
  display: flex;
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

input {
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
</style>
