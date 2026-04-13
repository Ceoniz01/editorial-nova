<template>
  <div class="app">

    <!-- contenido -->
    <div class="content">
      <router-view />
    </div>

    <!-- menú inferior -->
    <nav class="bottom-nav">
      <router-link to="/" class="btn">Inicio</router-link>
      <router-link to="/libros" class="btn">Libros</router-link>
    </nav>

  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style>
/* fondo general */
.app {
  min-height: 100vh;
  background: white;
  color: black;
  display: flex;
  flex-direction: column;
}

/* contenido centrado */
.content {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 20px;
}

/* menú inferior */
.bottom-nav {
  display: flex;
  justify-content: center;
  gap: 20px;
  padding: 15px;
  border-top: 1px solid #ddd;
  background: white;
  position: sticky;
  bottom: 0;
}

/* botones */
.btn {
  background: #1e88e5;
  color: white;
  padding: 10px 20px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: bold;
}

.btn:hover {
  background: #1565c0;
}
</style>