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
  data() {
    return {
      todos: [
        { id: 1, text: 'To do something cool' },
        { id: 2, text: 'Create a list of todos', checked: true },
        { id: 3, text: 'add router and one page for info', checked: true },
        {
          id: 4,
          text:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Saepe ad officiis maiores commodi assumenda sed dolore eaque quia quis praesentium.',
        },
      ],
    };
  },
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

.new-todo {
  margin-bottom: 2rem;
}

.todo-list {
  margin: 0;
  padding: 0;
  list-style: none;
}

.todo-item {
  margin-bottom: 0.5rem;
  transition: 0.3s;
}

.todo-item:last-of-type {
  margin-bottom: 0;
}
</style>
