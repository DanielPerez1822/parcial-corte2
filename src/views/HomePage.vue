<template>
  <BaseLayout>
    <div id="container">
      <strong>Bienvenido a la plataforma de Gestión de Reservas.</strong>
      <div class="buttons">
        <button @click="goToGestionReservasPage">Ir a Gestión de Reservas</button>
      </div>
    </div>
  </BaseLayout>
</template>

<script setup lang="ts">
import BaseLayout from '@/components/BaseLayout.vue';
import { useRouter } from 'vue-router';

const router = useRouter();

const goToGestionReservasPage = () => {
  router.push('/gestion-reservas').then(() => {
    router.go(0); // Force the page to refresh dynamically
  });
};
</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

.buttons {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  background-color: #0078D4;
  color: white;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #005a9e;
}
</style>
