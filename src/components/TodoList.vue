<template>
  <div class="items" v-for="(todo, index) in todos" :key="index">
    <todo-item class="item" @remove="$emit('remove', todo)" :todo="todo" />
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue';
export default {
  components: { TodoItem },
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
  methods: {

  },
};
</script>

<style scoped>
.items {
	display: flex;
	flex-direction: column;
}

.item {
	margin-top: 20px;
}
</style>
