<template>
  <header class="header">
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <span class="navbar-brand title">TodoList</span>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <router-link class="nav-link link" to="/">Home</router-link>
          <router-link class="nav-link link" to="/about">About</router-link>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'MainHeader',
};
</script>

<style scoped>
.title {
  cursor: default;
}

.router-link-exact-active {
  color: #fff !important;
}
</style>
