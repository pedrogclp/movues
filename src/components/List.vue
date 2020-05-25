<template>
  <div class="list">
    <h3>{{ title }}</h3>
    <ul>
      <li v-for="(elem, index) in filterFilms(films)" :key="index">
        <Film :film="elem" />
      </li>
    </ul>
  </div>
</template>

<script>
import Film from "./Film";

export default {
  name: "List",
  components: { Film },
  props: {
    filterByGenres: {},
  },
  data: () => {
    return {
      title: "Listado",
      films: [],
    };
  },
  created() {
    var that = this;
    fetch("/data.json")
      .then((response) => {
        return response.json();
      })
      .then((_data) => {
        that.$data.films = that.filterFilms(_data.films);
      });
  },
  methods: {
    filterFilms(films) {
      var that = this;
      return films.filter(function(film) {
        for (const genre of film.genres) {
          if (that.$props.filterByGenres.indexOf(genre.id) > -1) {
            return true;
          }
        }
        return false;
      })
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* Lista de películas */
.list {
  list-style: none;
  margin: 10px;
}
.list ul {
  list-style: none;
  padding: 0;
  display: flex;
  flex-flow: row wrap;
}

.list ul li {
  flex: 1 1 auto;
  display: flex;
  flex-flow: row wrap;
  align-items: flex-start;
  justify-content: center;
}
</style>
