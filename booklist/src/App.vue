<template>
  <div class="container">
    <!-- título -->
    <h1>BookList</h1>

    <!-- nombre -->
    <p>Hola, {{ nombre }}</p>
    <input v-model="nombre" placeholder="Escribe tu nombre" />

    <!-- contador -->
    <h2>Contador: {{ contador }}</h2>
    <button @click="sumar">Sumar</button>
    <button @click="restar">Restar</button>

    <!-- lista de libros -->
    <h2>Lista de libros</h2>

    <!-- formulario -->
    <h3>Agregar libro</h3>

    <!-- input título -->
    <input v-model="nuevoTitulo" placeholder="Título" />

    <!-- input autor -->
    <input v-model="nuevoAutor" placeholder="Autor" />

    <!-- botón agregar -->
    <button @click="agregarLibro">Agregar</button>

    <!-- mensaje si no hay libros -->
    <p v-if="libros.length === 0">No hay libros disponibles</p>

    <!-- listado -->
    <ul>
      <li v-for="(libro, index) in libros" :key="index">
        {{ libro.titulo }} - {{ libro.autor }}
      </li>
    </ul>
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

      // lista de libros
      libros: [
        { titulo: "Harry Potter", autor: "J.K. Rowling" },
        { titulo: "El Señor de los Anillos", autor: "Tolkien" },
      ],

      // nuevo libro
      nuevoTitulo: "",
      nuevoAutor: "",
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

    // agregar libro
    agregarLibro() {
      if (this.nuevoTitulo && this.nuevoAutor) {
        this.libros.push({
          titulo: this.nuevoTitulo,
          autor: this.nuevoAutor,
        });

        this.nuevoTitulo = "";
        this.nuevoAutor = "";
      }
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