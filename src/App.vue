<template>
  <div class="container">
    <custom-button class="dialog__btn" @click="showDialog">Добавить новую задачу</custom-button>
    <custom-dialog v-model:show="dialogVisible">
      <todo-form @add="addTask" />
    </custom-dialog>
    <todo-list @remove="deleteTask" :todos="todos" />
  </div>
</template>

<script>
import TodoForm from '@/components/TodoForm.vue';
import TodoList from '@/components/TodoList.vue';
import axios from 'axios';
export default {
  components: { TodoForm, TodoList },
  data() {
    return {
      todos: [],
      dialogVisible: false,
    };
  },
  methods: {
    addTask(task) {
      this.todos.push(task);
      this.dialogVisible = false;
    },
    deleteTask(post) {
      this.todos = this.todos.filter((todo) => todo.id !== post.id);
    },
    showDialog() {
      this.dialogVisible = true;
    },

    async fetchTodos() {
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=5');
        this.todos = response.data;
      } catch (error) {
        alert('ошибка при получении задач');
      }
    },
  },
  mounted() {
    this.fetchTodos();
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  margin: 10px auto;
  max-width: 40%;
}
</style>
