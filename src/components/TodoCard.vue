<template>
  <div class="todo-card">
    <input type="checkbox" />
    <p class="todo-text">Lorem ipsum dolor sit amet consectetur.</p>
    <b-button variant="danger">&times;</b-button>
  </div>
</template>

<script>
export default {
  name: "TodoCard",
};
</script>

<style scoped>
.todo-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 2rem;
  max-width: 50rem;
  border: 1px solid #2c3e5066;
  border-radius: 4px;
}

.todo-card:hover,
.todo-card:focus {
  box-shadow: 0 0 4px 1px #2c3e5066;
}

.todo-text {
  margin: 0;
  padding: 0;
}
</style>
