<template>
  <div class="auth-container">
    <div class="form-toggle">
      <button :class="{ active: isLogin }" @click="isLogin = true">Login</button>
      <button :class="{ active: !isLogin }" @click="isLogin = false">Sign Up</button>
    </div>

    <form @submit.prevent="isLogin ? login() : signup()">
      <div v-if="!isLogin">
        <input v-model="fullName" type="text" placeholder="Full Name" required />
        <input v-model="phone" type="tel" placeholder="Phone Number" required />
      </div>

      <input v-model="email" type="email" placeholder="Email" required />
      <input v-model="password" type="password" placeholder="Password" required />
      <button type="submit">{{ isLogin ? 'Login' : 'Sign Up' }}</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const emit = defineEmits(['login-success'])

const isLogin = ref(true)

const email = ref('')
const password = ref('')
const fullName = ref('')
const phone = ref('')

function login() {
  if (email.value && password.value) {
    emit('login-success')
  } else {
    alert('Please fill in all login fields.')
  }
}

function signup() {
  if (fullName.value && phone.value && email.value && password.value) {
    isLogin.value = true // Switch to login form
    // Optionally reset signup fields
    fullName.value = ''
    phone.value = ''
    password.value = ''
    email.value = ''
  } else {
    alert('Please fill in all signup fields.')
  }
}
</script>

<style scoped>
.auth-container {
  max-width: 350px;
  margin: 2rem auto;
  padding: 2rem;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(255, 255, 255, 0.1);
  color: #000;
}

.form-toggle {
  display: flex;
  justify-content: space-between;
  margin-bottom: 1rem;
}

.form-toggle button {
  flex: 1;
  padding: 0.5rem;
  background: #f0f0f0;
  border: none;
  cursor: pointer;
  font-weight: bold;
  transition: background 0.3s;
  border-radius: 5px 5px 0 0;
}

.form-toggle button.active {
  background-color: #d4a353;
  color: white;
}

form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

input {
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 1rem;
}

button[type="submit"] {
  background-color: #d4a353;
  color: white;
  padding: 0.5rem;
  border: none;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
}

button[type="submit"]:hover {
  background-color: #d4a353;
}
</style>







