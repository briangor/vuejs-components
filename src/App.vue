<template>
  <div id="app">
    <NavBar/>
    <HomePage title="Home" />
    <AboutPage />
    <ContactPage />
    <FooterComp/>
  </div>
</template>
<script>

import NavBar from './components/NavBar.vue';
import HomePage from './components/HomePage.vue';
import AboutPage from './components/pages/AboutPage.vue';
import ContactPage from './components/pages/ContactPage.vue';
import FooterComp from './components/FooterComp.vue';

export default {
  name: 'App',
  components: {
    HomePage,
    NavBar,
    AboutPage,
    ContactPage,
    FooterComp,
}
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}
</style>
