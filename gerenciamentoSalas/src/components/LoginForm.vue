<template>
  <form class="login-form" @submit.prevent="onSubmit">
    <div class="form-group">
      <label for="email">Email</label>
      <input type="email" id="email" v-model="email" class="input-field" required />
    </div>

    <div class="form-group">
      <label for="password">Senha</label>
      <input type="password" id="password" v-model="password" class="input-field" required />
    </div>

    <button type="submit" class="login-button">Login</button>
  </form>
</template>

<script setup>
import { ref } from 'vue';

const email = ref('');
const password = ref('');

function onSubmit() {
  console.log('Login submitted', email.value, password.value);
}
</script>

<style scoped>
/* Estilos específicos para o formulário de login */
.login-form {
  background-color: #d4d4d4;
  padding: 60px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 300px;
  display: flex;
  flex-direction: column;
}

.form-group {
  margin-bottom: 15px;
}

.label {
  font-size: 0.9rem;
  color: #fff;
  margin-bottom: 5px;
}

.input-field {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1rem;
}

.login-button {
  padding: 10px;
  background-color:  #28a745;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.login-button:hover {
  background-color:  #50c878;
}
</style>
