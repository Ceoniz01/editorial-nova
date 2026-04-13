<template>
  <div>
    <h1>Lista de Libros</h1>

    <h3>Agregar libro</h3>

    <input v-model="nuevoTitulo" placeholder="Título" />
    <input v-model="nuevoAutor" placeholder="Autor" />

    <button @click="agregarLibro">Agregar</button>

    <p v-if="libros.length === 0">No hay libros</p>

    <ul>
      <li v-for="(libro, index) in libros" :key="index">
        {{ libro.titulo }} - {{ libro.autor }}

        <button @click="eliminarLibro(index)">Eliminar</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ListaLibros",

  data() {
    return {
      libros: [
        { titulo: "Harry Potter", autor: "J.K. Rowling" },
        { titulo: "El Señor de los Anillos", autor: "Tolkien" },
      ],

      nuevoTitulo: "",
      nuevoAutor: "",
    };
  },

  methods: {
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

    eliminarLibro(index) {
      this.libros.splice(index, 1);
    },
  },
};
</script>