<template>
  <form @submit.prevent>
    <h2>Добавьте новую задачу</h2>
    <custom-input v-model="task.title" class="input" type="text" placeholder="Название" />
    <custom-input v-model="task.body" class="input" type="text" placeholder="Описание" />
    <custom-button class="btn" @click="addTask">Создать</custom-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      task: {
        title: '',
        body: '',
      },
    };
  },
  methods: {
    addTask() {
      this.task.id = Date.now();
      this.$emit('add', this.task);
      this.task = {
        title: '',
        body: '',
      };
    },
  },
};
</script>

<style lang="scss" scoped>
h2 {
  text-align: center;
  margin-bottom: 7px;
}

.input {
  margin-bottom: 10px;
}
.btn {
  margin-top: 5px;
  border: 2px solid blueviolet;
  color: blueviolet;
  width: 100%;

  &:hover {
    background: blueviolet;
  }
}
</style>
