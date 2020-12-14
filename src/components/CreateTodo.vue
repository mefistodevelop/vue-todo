<template>
  <div class="create-todo">
    <form class="form" name="create-todo" @submit="handleSubmit">
      <!-- <input
        type="text"
        class="form-field todo-title"
        name="todo-title"
        placeholder="Enter a title"
        aria-label="Enter a title"
        v-model="title"
      /> -->
      <textarea
        name="todo-text"
        cols="30"
        rows="1"
        placeholder="To do..."
        v-model="text"
        class="form-field todo-text"
        @focus="onFocus"
      />

      <footer class="form-footer" v-show="inFocus">
        <button
          type="submit"
          class="button submit-button"
          disabled="isDisabled"
        >
          Save
        </button>
        <button type="button" class="button cancel-button" @click="handleClear">
          Cancel
        </button>
      </footer>
    </form>
  </div>
</template>

<script>
export default {
  name: 'CreateTodo',
  data() {
    return {
      title: '',
      text: '',
      inFocus: false,
      isDisabled: true,
    };
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault();
      const trimmedText = this.text.trim();
      const trimmedTitle = this.title.trim();

      if (trimmedText || trimmedTitle) {
        console.log(`title: ${trimmedTitle}; text: ${trimmedText}`);
        this.$emit('create-todo', { title: trimmedTitle, text: trimmedText });
        this.title = '';
        this.text = '';
        this.onBlur();
      }
      return;
    },
    handleClear() {
      this.text = '';
      this.onBlur();
    },
    onFocus() {
      this.inFocus = true;
    },
    onBlur() {
      this.inFocus = false;
    },
  },
};
</script>

<style scoped>
.create-todo {
  padding: 1rem;
  background-color: #fff;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
}

.form {
  width: 100%;
  text-align: left;
}

.form-field {
  margin: 0;
  margin-bottom: 1rem;
  width: 100%;
  min-height: 44px;
  color: #424242;
  border: none;
  outline: none;
}

.form-field::placeholder {
  color: #9e9e9e;
  font-weight: 700;
  font-size: 0.9rem;
}

.todo-title {
  font-weight: 700;
}

.todo-text {
  margin-bottom: 0;
  min-height: 44px;
  overflow: hidden;
  resize: none;
  overflow-y: auto;
}

.form-footer {
  text-align: right;
}

.button {
  border: none;
  background-color: #fff;
  font-weight: 700;
}

.submit-button {
  color: #00c853;
  margin-right: 1rem;
}

.cancel-button {
  color: #bd2130;
}
</style>
