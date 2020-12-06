<template>
  <div class="todo-card">
    <input class="checkbox" type="checkbox" v-bind:checked="checked" />
    <p class="text" v-bind:class="{ 'crossed-out': checked }">{{ text }}</p>
    <b-button variant="danger">&times;</b-button>
  </div>
</template>

<script>
export default {
  name: "TodoCard",
  props: {
    text: {
      type: String,
      default: "",
    },
    checked: {
      type: Boolean,
      default: false,
    },
  },
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

.checkbox {
  margin-right: 2rem;
}

.text {
  margin: 0;
  padding: 0;
  margin-right: 2rem;
}

.crossed-out {
  text-decoration: line-through;
}
</style>
