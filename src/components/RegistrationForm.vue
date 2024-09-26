<template>
  <div>
    <h1>Регистрация</h1>
    <form @submit.prevent="register">
      <div>
        <label for="firstName">Имя:</label>
        <input
            type="text"
            v-model="firstName"
            :class="{ 'input-error': !firstName && submitted }"
        />
      </div>
      <div>
        <label for="lastName">Фамилия:</label>
        <input
            type="text"
            v-model="lastName"
            :class="{ 'input-error': !lastName && submitted }"
        />
      </div>
      <div>
        <label for="email">Почта:</label>
        <input
            type="email"
            v-model="email"
            :class="{ 'input-error': !email && submitted }"
        />
      </div>
      <div>
        <label for="password">Пароль:</label>
        <input
            type="password"
            v-model="password"
            :class="{ 'input-error': !password && submitted }"
        />
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
      errorMessage: '',
      submitted: false
    };
  },
  methods: {
    register() {
      this.submitted = true;

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

.input-error {
  border: 2px solid red;
}
form {
  display: flex;
  flex-direction: column;
  width: 300px;
  margin: 0 auto;
}
</style>
