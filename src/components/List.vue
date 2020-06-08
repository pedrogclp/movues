<template>
  <div class="list">
    <ul>
      <li>
        <div class="film">
          <div class="poster">
            <img
              src="https://image.tmdb.org/t/p/w400/d1QKiYtceF3GDtxvTFXFAqwwah9.jpg"
              alt="Titulo de película"
            />
          </div>
          <div class="data">
            <h2>Interestelar</h2>
            <h4>
              La humanidad nació en la Tierra. Nunca estuvo destinada a
              morir aquí.
            </h4>
            <ul class="genre">
              <li>Aventura</li>
              <li>Drama</li>
              <li>Ciencia ficción</li>
            </ul>
            <p class="overview" onclick="this.classList.toggle('hide')">
              Narra las aventuras de un grupo de exploradores que hacen uso
              de un agujero de gusano recientemente descubierto para superar
              las limitaciones de los viajes espaciales tripulados y vencer
              las inmensas distancias que tiene un viaje interestelar.
            </p>
          </div>
        </div>
      </li>
      <li>
        <div class="film">
          <div class="poster">
            <img
              src="https://image.tmdb.org/t/p/w400/od2A7qPtpimcYfqfKXkpHqoKyuS.jpg"
              alt="Titulo de película"
            />
          </div>
          <div class="data">
            <h2>Green Book</h2>
            <h4>Inspirada por una amistad verdadera.</h4>
            <ul class="genre">
              <li>Drama</li>
              <li>Comedia</li>
            </ul>
            <p class="overview" onclick="this.classList.toggle('hide')">
              Años 60. Cuando Tony Lip (Viggo Mortensen), un rudo
              italoamericano del Bronx, es contratado como chófer del
              virtuoso pianista negro Don Shirley (Mahershala Ali), durante
              una gira de conciertos por el Sur de Estados Unidos, deberá
              confiar en \"El libro verde\", una guía de los pocos
              establecimientos seguros para los afroamericanos, para
              encontrar alojamiento. Son dos personas que tendrán que hacer
              frente al racismo y los prejuicios, pero a las que la bondad y
              el sentido del humor unirán, obligándoles a dejar de lado las
              diferencias para sobrevivir y prosperar en el viaje de su
              vida.
            </p>
          </div>
        </div>
      </li>
      <li>
        <div class="film">
          <div class="poster">
            <img
              src="https://image.tmdb.org/t/p/w400/br6krBFpaYmCSglLBWRuhui7tPc.jpg"
              alt="Titulo de película"
            />
          </div>
          <div class="data">
            <h2>Avengers: Endgame</h2>
            <h4>Nada puede prepararte para el final.</h4>
            <ul class="genre">
              <li>Acción</li>
              <li>Aventura</li>
              <li>Ciencia ficción</li>
            </ul>
            <p class="overview" onclick="this.classList.toggle('hide')">
              Después de los eventos devastadores de 'Vengadores: Infinity
              War', el universo está en ruinas debido a las acciones de
              Thanos. Con la ayuda de los aliados que quedaron, los
              Vengadores deberán reunirse una vez más para intentar deshacer
              sus acciones y restaurar el orden en el universo de una vez
              por todas, sin importar cuáles sean las consecuencias...
              Cuarta y última entrega de la saga "Vengadores".
            </p>
          </div>
        </div>
      </li>
      <li>
        <div class="film">
          <div class="poster">
            <img
              src="https://image.tmdb.org/t/p/w400/i3WnZpJkQYXXbSGplEGmyoyeskM.jpg"
              alt="Titulo de película"
            />
          </div>
          <div class="data">
            <h2>Zootopia</h2>
            <h4>Bienvenidos a la jungla urbana.</h4>
            <ul class="genre">
              <li>Animación</li>
              <li>Aventura</li>
              <li>Comedia</li>
              <li>Familia</li>
            </ul>
            <p class="overview" onclick="this.classList.toggle('hide')">
              La moderna metrópoli mamífera de Zootrópolis es una ciudad
              absolutamente única. Está compuesta de barrios con diferentes
              hábitats como la lujosa Plaza Sahara, el Distrito Selva
              Tropical y el gélido Distrito Tundra. Es un crisol donde los
              animales de cada entorno conviven, un lugar donde no importa
              lo que seas. De hecho puedes ser cualquier cosa, desde un
              elefante enorme hasta la musaraña más diminuta. Pero cuando
              llega la optimista agente Judy Hopps, descubre que ser la
              primera conejita de un cuerpo policial compuesto de animales
              duros y enormes no es nada fácil. Pero está decidida a
              demostrar su valía y se mete de cabeza en un caso, a pesar de
              que eso significa trabajar con Nick Wilde, un zorro parlanchín
              y estafador, para resolver el misterio.
            </p>
          </div>
        </div>
      </li>
      <li>
        <div class="film">
          <div class="poster">
            <img
              src="https://image.tmdb.org/t/p/w400/jnFCk7qGGWop2DgfnJXeKLZFuBq.jpg"
              alt="Titulo de película"
            />
          </div>
          <div class="data">
            <h2>Frozen II</h2>
            <h4>Sé fuerte. Enfréntate a tus miedos.</h4>
            <ul class="genre">
              <li>Animación</li>
              <li>Familia</li>
              <li>Aventura</li>
            </ul>
            <p class="overview" onclick="this.classList.toggle('hide')">
              ¿Por qué nació Elsa con poderes mágicos? La respuesta le está
              llamando y amenaza su reino. Junto con Anna, Kristoff, Olaf y
              Sven emprenderá un viaje peligroso e inolvidable. En 'Frozen:
              El Reino del Hielo', Elsa temía que sus poderes fueran
              demasiado para el mundo. En 'Frozen 2', deseará que sean
              suficientes.
            </p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "List",
  // Nuestros componentes
  components: {},
  methods: {},
  computed: {}
};
</script>
<style>
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