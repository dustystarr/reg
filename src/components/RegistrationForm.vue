<template>
  <div>
    <h1>Регистрация</h1>
    <form @submit.prevent="register">
      <div>
        <label for="firstName">Имя:</label>
        <input type="text" v-model="firstName" required />
      </div>
      <div>
        <label for="lastName">Фамилия:</label>
        <input type="text" v-model="lastName" required />
      </div>
      <div>
        <label for="email">Почта:</label>
        <input type="email" v-model="email" required />
      </div>
      <div>
        <label for="password">Пароль:</label>
        <input type="password" v-model="password" required />
      </div>
      <button type="submit">Зарегистрироваться</button>
    </form>
    <div v-if="errorMessage" style="color: red;">{{ errorMessage }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
      password: '',
      errorMessage: ''
    };
  },
  methods: {
    register() {
      if (!this.firstName || !this.lastName || !this.email || !this.password) {
        this.errorMessage = 'Пожалуйста, заполните все поля.';
      } else {
        this.errorMessage = '';
        alert('Регистрация успешна!');
      }
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  width: 300px;
  margin: 0 auto;
}
</style>
