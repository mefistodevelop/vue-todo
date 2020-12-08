<template>
  <div class="todo-card">
    <div class="checkbox">
      <CheckboxButton :isChecked="completed" @mark-completed="markCompleted" />
    </div>
    <p class="text" v-bind:class="{ 'crossed-out': completed }">{{ text }}</p>
    <b-button variant="danger" @click="$emit('remove-todo')">&times;</b-button>
  </div>
</template>

<script>
import CheckboxButton from './common/CheckboxButton';

export default {
  name: 'TodoCard',
  components: { CheckboxButton },
  props: {
    text: {
      type: String,
      default: '',
    },
    isChecked: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      completed: this.isChecked,
    };
  },
  methods: {
    markCompleted(mark) {
      this.completed = mark;
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
