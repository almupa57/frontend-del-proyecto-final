<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/> -->
    <header class="header-section">
    <div class="header-container">
      <div class="site-title">
        <h1>Diseñaste?...!Yo te lo presupuesto¡</h1>
      </div>

      <!-- Inicio menú navegación -->
      <nav class="site-nav">
        <router-link to="/" class="link">
          Inicio
        </router-link>
        <a href="#services">Servicios</a>
        <a href="#news">Noticias</a>
        <a href="#team">Nuestro equipo</a>
      </nav>
      <!-- Fin menú navegación -->

      <div class="logo-container">
        <img
          class="logo-container__site-logo"
          src="./assets/logomision.png"
          alt="Logo MisionTic 2022"
        />
      </div>
    </div>
   </header>
  <!-- fin encabezado del sitio -->

  <router-view />

  <!-- Inicio pie del sitio -->
  <footer class="footer-section">
    <article>
      <h2>Contacto</h2>
      <p>
        Somos una empresa preocupada por su tiempo, su dinero y por supuesto, su
        bienestar
      </p>
      <p>
        Urbanización Santa Clara-Carrera 14 Mz. K lote 12, Cartagena, Colombia
      </p>
      <p>celular: 3106480107</p>
      <p>email: almupa57@gmail.com</p>
    </article>
    <article>
      <h2>Otra Información</h2>
      <p>
        Si usted ya lo diseñó, con esta aplicación calcule las cantidades de
        obra, cantidades de materiales, el presupuesto y obtenga el informe de
        resultados
      </p>
      <p>email: almupa57</p>
      <p>http://127.0.0.1:5501/src/index2.html</p>
    </article>
  </footer>
  <!-- fin pie del sitio -->


  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
/* 
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
} */

.header-section {
  margin-bottom: 100px;
}

.header-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  text-align: center;
}

.site-title {
  width: 30%;
  background-color: #334979;
  color: white;
}

.site-nav {
  width: 40%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: #334979;
}

.site-nav > a {
  color: white;
  text-decoration: none;
}

.link {
  text-decoration: none;
}

.site-nav > a:hover {
  text-decoration: underline;
  font-weight: bold;
}

.logo-container {
  width: 30%;
  background-color: #334979;
}

.logo-container__site-logo {
  height: 80px;
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

.footer-section {
  background-color: #25294f;
  height: 200px;
  display: flex;
  color: white;
  justify-content: space-evenly;
}

</style>
