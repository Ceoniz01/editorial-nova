<template>
  <div class="container">
    <!-- título -->
    <h1>BookList</h1>

    <!-- nombre del usuario -->
    <p>Hola, {{ nombre }}</p>

    <!-- input -->
    <input v-model="nombre" placeholder="Escribe tu nombre" />

    <!-- contador -->
    <h2>Contador: {{ contador }}</h2>

    <!-- botón sumar -->
    <button @click="sumar">Sumar</button>

    <!-- botón restar -->
    <button @click="restar">Restar</button>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      // nombre usuario
      nombre: "",

      // contador
      contador: 0,
    };
  },

  methods: {
    // sumar contador
    sumar() {
      this.contador++;
    },

    // restar contador
    restar() {
      this.contador--;
    },
  },
};
</script>

<style>
/* contenedor */
.container {
  padding: 20px;
  font-family: Arial;
}

/* botones */
button {
  margin: 5px;
  padding: 10px;
}
</style>