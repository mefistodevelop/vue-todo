<template>
  <div class="home">
    <h1>TODO</h1>
    <div class="new-todo">
      <CreateTodo @create-todo="createTodo" />
    </div>
    <ul class="todo-list">
      <li class="todo-item" :key="todo.id" v-for="todo in todos">
        <TodoCard
          v-bind:text="todo.text"
          v-bind:isChecked="todo.checked"
          @remove-todo="removeTodo(todo.id)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import CreateTodo from '../components/CreateTodo';
import TodoCard from '../components/TodoCard';

export default {
  name: 'HomePage',
  components: { CreateTodo, TodoCard },
  data() {
    return {};
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },

    createTodo({ text, title }) {
      const newTodo = {
        title,
        text,
        id: this.todos[this.todos.length - 1].id + 1,
      };

      this.todos.push(newTodo);
    },
  },
};
</script>
