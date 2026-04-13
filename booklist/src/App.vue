<template>
  <div>
    <!-- menú simple -->
    <nav>
      <router-link to="/">Inicio</router-link> |
      <router-link to="/libros">Libros</router-link>
    </nav>

    <!-- aquí se cargan las vistas -->
    <router-view />
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

    // eliminar libro
    eliminarLibro(index) {
      this.libros.splice(index, 1);
    }
  }
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