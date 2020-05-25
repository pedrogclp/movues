<template>
  <div class="list">
    <h3>{{ title }}</h3>
    <ul>
      <li v-for="(elem, index) in films" :key="index">
        <Film :film="elem" />
      </li>
    </ul>
  </div>
</template>

<script>
import Film from "./Film";
import dataJson from "../data/data.json";

export default {
  name: "List",
  components: { Film },
  data: () => {
    return Object.assign({ title: "Listado" }, dataJson);
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
