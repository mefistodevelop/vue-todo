<template>
  <div id="app">
    <MainHeader />
    <main class="container">
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
import MainHeader from './components/MainHeader';
import HomePage from './pages/HomePage';
import AboutPage from './pages/AboutPage';
import VueRouter from 'vue-router';

export default {
  name: 'App',
  components: { MainHeader },
  router: new VueRouter({
    mode: 'history',
    routes: [
      { path: '/', component: HomePage },
      { path: '/about', component: AboutPage },
    ],
  }),
};
</script>

<style scoped>
#app {
  font-family: 'Montserrat', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}

.container {
  margin: 0 auto;
  max-width: 50rem;
  width: 100%;
}
</style>
