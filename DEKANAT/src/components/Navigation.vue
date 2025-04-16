<script setup lang="ts">
</script>

<template>
  <nav class="navigation">
    <button class="nav-button">Для Преподавателей</button>
    <button class="nav-button">Для Студента</button>
    <button class="nav-button">Учебные Планы</button>
  </nav>
</template>

<style scoped>
.navigation {
  position: fixed;
  top: 70px;
  left: 0;
  right: 0;
  width: 100%;
  background-color: rgba(26, 35, 126, 0.8);
  padding: 1rem;
  display: flex;
  justify-content: center;
  gap: 2rem;
  z-index: 99;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.nav-button {
  background-color: transparent;
  color: white;
  border: 2px solid #646cff;
  padding: 0.8rem 1.5rem;
  cursor: pointer;
  font-weight: 500;
  transition: all 0.3s ease;
  font-size: 1.1rem;
  min-width: 200px;
}

.nav-button:hover {
  background-color: #646cff;
  border-color: #646cff;
  transform: translateY(-2px);
}

.nav-button:active {
  transform: translateY(0);
}
</style>