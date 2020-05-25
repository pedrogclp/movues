<template>
  <!-- Contenido de la aplicación -->
  <div id="app">
    <header>
      <h1>🍿 MoVues</h1>
    </header>
    <div class="main-content">
      <Aside v-on:updateFilter="updateGenres($event)" />
      <List :filterByGenres="filterByGenres"/>
    </div>
  </div>
</template>

<script>
// Import de nuestros componentes
import Aside from "./components/Aside.vue";
import List from "./components/List.vue";

export default {
  name: "MoVues",
  data() {
    return {
      filterByGenres: [],
    };
  },
  // Nuestros componentes
  components: {
    Aside,
    List,
  },
  methods: {
    updateGenres (event) {
      this.filterByGenres = event;
    },
  },
};
</script>

<style>
/** Me gusta quitar los márgenes al body */
body {
  margin: 0;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
/* Header */
header {
  background-color: #4fc08d;
  padding: 15px 15px;
  text-align: left;
}

header h1,
small {
  margin: 0;
  color: #fff;
}

/* Estructura */
.main-content {
  display: flex;
}

@media screen and (max-width: 600px) {
  .main-content {
    flex-flow: column;
  }
}
</style>
