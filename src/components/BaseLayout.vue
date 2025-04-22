<template>
  <div class="base-layout">
    <header class="header">
      <h1>Sistema de Gestión</h1>
    </header>
    <main class="content">
      <slot />
    </main>
    <footer class="footer">
      <p>&copy; 2023 Sistema de Gestión. Todos los derechos reservados.</p>
    </footer>
  </div>
</template>

<style scoped>
.base-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: Arial, sans-serif;
}

.header {
  background-color: #0078d4;
  color: white;
  padding: 20px;
  text-align: center;
}

.content {
  flex: 1;
  padding: 20px;
  background-color: #f9f9f9;
}

.footer {
  background-color: #0056b3;
  color: white;
  text-align: center;
  padding: 10px;
}
</style>
