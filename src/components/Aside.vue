<template>
  <div class="filter">
    <div class="control-group">
      <h2>{{ title }}</h2>
      <label
        v-for="(elem, index) in genres"
        :key="index"
        class="control control--checkbox"
      >
        {{ elem.name }}
        <input
          type="checkbox"
          :value="elem.id"
          :checked="filterByGenres.indexOf(elem.id) > -1"
          @click="addOrDeleteGenre(elem)"
        />
        <div class="control__indicator"></div>
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: "Aside",
  data() {
    return {
      title: "Filtro por género",
      genres: [],
      filterByGenres: [],
    };
  },
  methods: {
    addOrDeleteGenre(genre) {
      var index = this.filterByGenres.indexOf(genre.id);
      if (index === -1) {
        this.filterByGenres.push(genre.id);
      } else {
        this.filterByGenres.splice(index, 1);
      }
      this.emitUpdateFilter();
    },
    getUniqueGenresFromFilms(films) {
      var y = [];
      films.map((film) => film.genres.map((genre) => y.push(genre)));
      return [...new Set(y.map((genre) => JSON.stringify(genre)))].map((z) =>
        JSON.parse(z)
      );
    },
    emitUpdateFilter() {
      this.$emit('updateFilter', this.filterByGenres);
    }
  },
  created() {
    var that = this;
    fetch("/data.json")
      .then((response) => {
        return response.json();
      })
      .then((_data) => {
        that.$data.genres = that.getUniqueGenresFromFilms(_data.films);
        that.$data.filterByGenres = that
          .getUniqueGenresFromFilms(_data.films)
          .map((genre) => genre.id);
        this.emitUpdateFilter();
      });
  },
};
</script>

<style scoped>
/* Filtros de búsqueda */
.filter {
  flex: 1 1 auto;
  display: flex;
  align-items: flex-start;
  justify-content: center;
}

/* Copy / paste: Kenan Yusuf : https://codepen.io/KenanYusuf/pen/PZKEKd */
.control-group {
  display: inline-block;
  vertical-align: top;
  background: #fff;
  text-align: left;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  padding: 30px;
  width: 200px;
  margin: 10px;
}
.control {
  display: block;
  position: relative;
  padding-left: 30px;
  margin-bottom: 15px;
  cursor: pointer;
  font-size: 18px;
}
.control input {
  position: absolute;
  z-index: -1;
  opacity: 0;
}
.control__indicator {
  position: absolute;
  top: 2px;
  left: 0;
  height: 20px;
  width: 20px;
  background: #e6e6e6;
}
.control--radio .control__indicator {
  border-radius: 50%;
}
.control:hover input ~ .control__indicator,
.control input:focus ~ .control__indicator {
  background: #ccc;
}
.control input:checked ~ .control__indicator {
  background: #4fc08d;
}
.control:hover input:not([disabled]):checked ~ .control__indicator,
.control input:checked:focus ~ .control__indicator {
  background: #338f66;
}
.control input:disabled ~ .control__indicator {
  background: #e6e6e6;
  opacity: 0.6;
  pointer-events: none;
}
.control__indicator:after {
  content: "";
  position: absolute;
  display: none;
}
.control input:checked ~ .control__indicator:after {
  display: block;
}
.control--checkbox .control__indicator:after {
  left: 8px;
  top: 4px;
  width: 3px;
  height: 8px;
  border: solid #fff;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}
.control--checkbox input:disabled ~ .control__indicator:after {
  border-color: #7b7b7b;
}
.control--radio .control__indicator:after {
  left: 7px;
  top: 7px;
  height: 6px;
  width: 6px;
  border-radius: 50%;
  background: #fff;
}
.control--radio input:disabled ~ .control__indicator:after {
  background: #7b7b7b;
}
</style>
