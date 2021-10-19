<template>
  <!-- <div class="home"> -->
  <div>
    <div class="banner">
      <img src="../assets/FOTOSPRINT.png" alt="A banner image" />
    </div>

        <!-- inicio contenido principal -->
    <main>
      <section>Servicios</section>
      <!-- inicio sección de servicios -->
      <section id="services" class="services-section">
        <!-- <router-link to="/presupuesto"> -->
        <article class="services-info">
          <img
            class="services-info__imagen"
            src="../assets/Cantidades.png"
          />
          <h2 class="services-info__title">Cuantificación de obra</h2>
          <p class="services-info__text">
            A través de esta aplicación, usted a través de un click podrá
            conocer las cantidades de obra iniciales de una instalación
            eléctrica tipo interés social de hasta 3 plantas, con una precisión
            del +/- 5%, lo cual se podra ajustar durante el desarrollo de la
            obra
          </p>

          <button class="btn btn-primary btn-block" @click="interes">
            Interes social=
          </button>
          <input
            type="text"
            value="Escriba cantidad de cuartos"
            name="nombredelacaja"
          />
        </article>
        <!-- </router-link> -->

        <article class="services-info">
          <router-link to="/presupuesto" class="link">
            <img
              class="services-info__imagen"
              src="../assets/Presupuesto.png"
              alt=""
            />
            <h2 class="services-info__title">Cálculo del presupuesto</h2>
          </router-link>
          <p class="services-info__text">
            Con esta aplicación, usted a través de un sólo click podrá
            determinar los costos de materiales a utilizar de acuerdo a las
            cantidades de obra iniciales de una instalación eléctrica de una
            edicficación tipo interés social de hasta 3 plantas, con una
            precisión del +/- 5%, lo cual ajustando las cantidades finales o
            parciales, automáticamente se ajusta el presupuesto a lo largo del
            desarrollo de la obra.
          </p>
        </article>

        <article class="services-info">
          <router-link to="/resultados" class="link">
            <img
              class="services-info__imagen"
              src="../assets/Resultados.png"
              alt=""
            />
            <h2 class="services-info__title">Informe de Resultados</h2>
          </router-link>
          <p class="services-info__text">
            Con esta aplicación, usted a través de un sólo click podrá Obtener
            un informe escrito en lenguaje de texto, que luego podrá reescriber
            en textos con el logotipo de su empresa u organización.
          </p>
        </article>
      </section>
      <!-- fin sección de servicios -->
      <news-section id="news">Noticias</news-section>
      <!-- inicio sección de noticias -->
      <news-section class="news-section">
        <article class="news-info">
          <div class="news-header">
            <img
              class="news-info__imagen"
              src="../assets/NoticiasDeportivas.png"
              alt=""
            />
            <h2 class="news-info__title">Noticias Deportivas</h2>
          </div>
          <p class="news-info__text">
            El argentino Paulo Dybala, el colombiano Juan Guillermo Cuadrado y
            el uruguayo Rodrigo Bentancur entraron este lunes en la lista del
            Juventus Turín para el estreno en la Liga de Campeones contra el
            …mas
          </p>
        </article>

        <article class="news-info">
          <div class="news-header">
            <img
              class="news-info__imagen"
              src="../assets/NoticiasMundo.png"
              alt=""
            />
            <h2 class="news-info__title">Noticias del Mundo</h2>
          </div>
          <p class="news-info__text">
            El primer juicio vinculado al escándalo de los sobornos pagados por
            familias para asegurar el acceso de sus hijos a prestigiosas
            universidades de Estados Unidos arrancó este lunes, con dos padres
            sentados en ... más
          </p>
        </article>

        <article class="news-info">
          <div class="news-header">
            <img
              class="news-info__imagen"
              src="../assets/NoticiasEconomia.png"
              alt=""
            />
            <h2 class="news-info__title">Noticias de Economía</h2>
          </div>
          <p class="news-info__text">
            Así será la primera tienda Ikea en Colombia Aunque no tiene
            presencia todavía en el país, la multinacional europea de muebles y
            decoración para el hogar Ikea goza de gran reconocimiento en
            Colombia. Por eso, en Bogotá ya se preparan para lo que será la
            primera tienda física de la marca sueca en el país … más
          </p>
        </article>

        <article class="news-info">
          <div class="news-header">
            <img
              class="news-info__imagen"
              src="../assets/NoticiasFarandula.png"
              alt=""
            />
            <h2 class="news-info__title">Noticias de Farándula</h2>
          </div>
          <p class="news-info__text">
            Ellos son los actores que le darán vida a la novela sobre Martín
            Elías Hoy a las 9 p.m. se estrena ‘El hijo del cacique’, una
            producción de ficción que cuenta la historia de Martín Elías, hijo
            del gran cantante vallenato Diomedes Díaz, desde sus … más
          </p>
        </article>
      </news-section>

      <team-Section id="team">Equipo</team-Section>
      <!-- inicio sección de equipo -->
      <team-section class="team-section">
        <article class="team-info">
          <img
            class="team-info__imagen"
            src="../assets/FotoActualizadaAlberto.png"
            alt=""
          />
          <h2 class="team-info__title">Alberto Murillo Padilla</h2>
          <p class="team-info__text">
            - Scrum Owner - Ing. Electricista - Especialista en Pedagogía para
            el Desarrollo del Aprendizaje Autónomo - Magister en Gestión de la
            Tecnología Educativa
          </p>
        </article>

        <article class="team-info">
          <img
            class="team-info__imagen"
            src="../assets/FotoPerfilIncognito.png"
            alt=""
          />
          <h2 class="team-info__title">Angela Lorena Trejos Ropero</h2>
          <p class="team-info__text">
            - Scrum Master - Abogada - XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX -
            XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
          </p>
        </article>

        <article class="team-info">
          <img
            class="team-info__imagen"
            src="../assets/FotoPerfilIncognito.png"
            alt=""
          />
          <h2 class="team-info__title">Jorge Alandete</h2>
          <p class="team-info__text">
            - Scrum Master - Abogada - XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX -
            XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
          </p>
        </article>

        <article class="team-info">
          <img
            class="team-info__imagen"
            src="../assets/FotoPerfilIncognito.png"
            alt=""
          />
          <h2 class="team-info__title">XXXXXXXXXXXXXXX</h2>
          <p class="team-info__text">
            - Scrum Master - Abogada - XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX -
            XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
          </p>
        </article>

      </team-section>
      <!-- fin sección de equipo -->

    </main>
    <!-- fin contenido principal -->

  </div>
</template>


<script>

export default {
  name: 'Home',
}
</script>


<style scoped>
* {
  box-sizing: border-box;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

body {
  max-width: 1400px;
  min-width: 375px;
  margin-right: auto;
  margin-left: auto;
  margin-top: 0;
  margin-bottom: 0;
  color: #222222;
}

.banner {
  width: 100%;
}

.banner > img {
  width: 100%;
  height: 800px;
  max-width: 1500px;
  object-fit: cover;
}

.services-section,
.news-section,
.team-section {
  display: flex;
  margin-bottom: 100px;
}

.news-section,
.header-container {
  background-color: #f7f7f7;
}

.news-section {
  flex-wrap: wrap;
}

.services-info {
  padding: 20px;
  text-align: center;
  text-decoration: none;
}

.link {
  text-decoration: none;
  color: #2c3e50;
}

.news-info {
  width: 50%;
  padding: 20px;
}

.news-header {
  display: flex;
  justify-content: space-around;
}

.news-info__title {
  align-self: center;
}

.services-info__imagen {
  border-radius: 50%;
  margin-right: auto;
  margin-left: auto;
}

.team-info {
  width: 25%;
  padding: 15px;
}

.team-info__imagen {
  display: block;
  margin-right: auto;
  margin-left: auto;
}
</style>
