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
  props: {},
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

<style scoped>
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
