<template>
  <div class="app">

    <!-- navbar superior SOLO en /libros -->
    <nav v-if="$route.path === '/libros'" class="top-nav">
      <router-link to="/" class="btn">Inicio</router-link>
      <router-link to="/libros" class="btn">Libros</router-link>
    </nav>

    <!-- contenido -->
    <div class="content">
      <router-view />
    </div>

    <!-- navbar inferior SOLO en inicio -->
    <nav v-if="$route.path === '/'" class="bottom-nav">
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
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;

  /* fondo tipo cuaderno */
  background: white;
  background-image: repeating-linear-gradient(
    to bottom,
    #ffffff,
    #ffffff 28px,
    #e0e0e0 29px
  );
  color: black;
}

.content {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
}

.top-nav,
.bottom-nav {
  display: flex;
  justify-content: center;
  gap: 20px;
  padding: 15px;
  border-top: 1px solid #ccc;
}

.bottom-nav {
  position: sticky;
  bottom: 0;
}

.btn {
  background: #0d47a1;
  color: white;
  padding: 10px 20px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: bold;
}

.btn:hover {
  background: #002171;
}
</style>