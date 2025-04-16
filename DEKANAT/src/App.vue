<script setup lang="ts">
import Header from './components/Header.vue'
import Navigation from './components/Navigation.vue'
</script>

<template>
  <div class="app-container">
    <Header />
    <Navigation />
    <main>
      <h2>Добро пожаловать в Виртуальный Деканат</h2>
    </main>
  </div>
</template>

<style>
body {
  margin: 0;
  min-height: 100vh;
  background: linear-gradient(135deg, #0f0f0f 0%, #1a237e 100%);
}

.app-container {
  min-height: 100vh;
  width: 100%;
}

main {
  padding: 2rem;
  text-align: center;
  margin-top: 120px;
  color: white;
}
</style>