<template>
  <div class="film">
    <div class="poster">
      <img :src="'https://image.tmdb.org/t/p/w400' + film.poster_path" :alt="film.title" />
    </div>
    <div class="data">
      <h2>{{ film.title }}</h2>
      <h4>{{ film.tagline }}</h4>
      <ul class="genre">
        <li v-for="(genre, index_genre) in film.genres" :key="index_genre">{{ genre.name }}</li>
      </ul>
      <p class="overview" onclick="this.classList.toggle('hide')">{{ film.overview }}</p>
    </div>
  </div>
</template>
<script>
export default {
  name: "Film",
  props: {
    film: {
      title: String,
      poster_path: String,
      tagline: String,
      overview: String,
      genres: [
        {
          name: String
        }
      ]
    }
  }
};
</script>
<style>
/* Tarjeta individual película */
.film {
  width: 300px;
  height: auto;
  overflow: hidden;
  margin: 10px;
  background-color: whitesmoke;
  border-radius: 5px;
  border: 1px solid #dedede;
  position: relative;
  box-sizing: border-box;
}
.poster {
  width: 100%;
  height: auto;
  overflow: hidden;
}
.poster img {
  width: 100%;
  height: auto;
}
.data {
  margin: 15px;
}
.data h2,
h4 {
  text-align: left;
  margin: 0;
}
.data .genre {
  display: inherit;
  position: relative;
  height: auto;
  overflow: hidden;
  padding: 10px 0;
}
.data .genre li {
  list-style: none;
  float: left;
  margin: 0 5px 3px 0;
  border-radius: 15px;
  padding: 3px 15px;
  background-color: #73abfe;
  color: #fff;
}
.data .overview {
  margin: 0;
  position: relative;
  text-align: left;
}
.data .overview.hide {
  margin: 0;
  position: relative;
  text-align: left;
  text-overflow: ellipsis;
  /* Se necesita para la ellipsis */
  overflow: hidden;
  white-space: nowrap;
}
</style>
