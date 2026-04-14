<template>
  <div class="libros">

    <h1>Lista de Libros</h1>

    <h3 class="subrayado">Agregar libro</h3>

    <div class="form">
      <input v-model="nuevoTitulo" placeholder="Título" />
      <input v-model="nuevoAutor" placeholder="Autor" />

      <button class="btn-agregar" @click="agregarLibro">
        Agregar
      </button>
    </div>

    <table v-if="libros.length > 0">
      <thead>
        <tr>
          <th>#</th>
          <th>Título</th>
          <th>Autor</th>
          <th>Acción</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="(libro, index) in libros" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ libro.titulo }}</td>
          <td>{{ libro.autor }}</td>
          <td>
            <button class="btn-eliminar" @click="eliminarLibro(index)">
              Eliminar
            </button>
          </td>
        </tr>
      </tbody>
    </table>

    <p v-else>No hay libros</p>

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

<style>
.libros {
  width: 100%;
  max-width: 700px;
  text-align: center;
}

.subrayado {
  text-decoration: underline;
}

.form {
  margin-bottom: 20px;
}

input {
  margin: 5px;
  padding: 8px;
}

/* botón agregar */
.btn-agregar {
  background: rgb(0, 152, 70);
  color: white;
  padding: 8px 15px;
  border: none;
  border-radius: 5px;
}

/* tabla */
table {
  width: 100%;
  border-collapse: collapse;
}

th, td {
  border: 1px solid #ccc;
  padding: 10px;
}

/* botón eliminar */
.btn-eliminar {
  background: red;
  color: white;
  padding: 5px 10px;
  border: none;
  border-radius: 5px;
}
</style>