<template>
  <div id="app">
    <Header />
    <main class="container">
      <h1>TODO</h1>
      <ul class="todo-list">
        <li class="todo-item" :key="todo.id" v-for="todo in todos">
          <TodoCard
            v-bind:text="todo.text"
            v-bind:isChecked="todo.checked"
            @remove-todo="removeTodo(todo.id)"
          />
        </li>
      </ul>
    </main>
  </div>
</template>

<script>
import Header from './components/Header';
import TodoCard from './components/TodoCard';

export default {
  name: 'App',
  components: { Header, TodoCard },
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
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
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

.todo-list {
  margin: 0;
  padding: 0;
  list-style: none;
}

.todo-item {
  margin-bottom: 0.5rem;
}

.todo-item:last-of-type {
  margin-bottom: 0;
}
</style>
