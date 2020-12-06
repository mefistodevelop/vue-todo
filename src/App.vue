<template>
  <div id="app">
    <Header />
    <main class="container">
      <h1>TODO</h1>
      <TodoCard />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header";
import TodoCard from "./components/TodoCard";

export default {
  name: "App",
  components: { Header, TodoCard },
};
</script>

<style scoped>
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}

.container {
  margin: 0 auto;
  max-width: 1400px;
  width: 100%;
}
</style>
