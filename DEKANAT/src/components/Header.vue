<script setup lang="ts">
import { ref } from 'vue';

const isModalOpen = ref(false);
const activeForm = ref<'login' | 'register' | null>(null);

const openModal = () => {
  isModalOpen.value = true;
};

const closeModal = () => {
  isModalOpen.value = false;
  activeForm.value = null;
};

const showLoginForm = () => {
  activeForm.value = 'login';
};

const showRegisterForm = () => {
  activeForm.value = 'register';
};
</script>

<template>
  <header class="header">
    <h1>ВИРТУАЛЬНЫЙ ДЕКАНАТ</h1>
    <button class="login-button" @click="openModal">ВХОД</button>

    <!-- Modal -->
    <div v-if="isModalOpen" class="modal-overlay">
      <div class="modal">
        <button class="close-button" @click="closeModal">&times;</button>
        <div class="modal-content">
          <h2>Авторизация</h2>
          
          <!-- Initial buttons -->
          <div v-if="!activeForm" class="button-group">
            <button class="modal-button" @click="showLoginForm">Войти</button>
            <button class="modal-button" @click="showRegisterForm">Зарегистрироваться</button>
          </div>

          <!-- Login Form -->
          <form v-if="activeForm === 'login'" class="auth-form" @submit.prevent>
            <div class="form-group">
              <input type="text" placeholder="ID" class="form-input" />
            </div>
            <div class="form-group">
              <input type="password" placeholder="Пароль" class="form-input" />
            </div>
            <button type="submit" class="modal-button">Войти</button>
          </form>

          <!-- Registration Form -->
          <form v-if="activeForm === 'register'" class="auth-form" @submit.prevent>
            <div class="form-group">
              <input type="text" placeholder="ФИО" class="form-input" />
            </div>
            <div class="form-group">
              <input type="password" placeholder="Пароль" class="form-input" />
            </div>
            <button type="submit" class="modal-button">Зарегистрироваться</button>
          </form>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: #1a1a1a;
  color: white;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  box-sizing: border-box;
  z-index: 100;
}

.login-button {
  background-color: #646cff;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  font-weight: bold;
}

.login-button:hover {
  background-color: #535bf2;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  position: relative;
  min-width: 300px;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 10px;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  color: #666;
}

.modal-content {
  color: #213547;
}

.modal-content h2 {
  margin-bottom: 1.5rem;
  text-align: center;
}

.button-group {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.modal-button {
  background-color: #646cff;
  color: white;
  border: none;
  padding: 0.8rem;
  cursor: pointer;
  font-weight: bold;
  width: 100%;
}

.modal-button:hover {
  background-color: #535bf2;
}

.auth-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.form-group {
  width: 100%;
}

.form-input {
  width: 100%;
  padding: 0.8rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
  box-sizing: border-box;
}

.form-input:focus {
  outline: none;
  border-color: #646cff;
}
</style>