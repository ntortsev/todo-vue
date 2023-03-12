<template>
  <div class="item">
    <div class="item__content">
      <h2>{{ todo.title }}</h2>
      <p>{{ todo.body }}</p>
    </div>
    <custom-button class="btn" @click="$emit('remove', todo)">Удалить</custom-button>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.item {
	padding: 10px;
	border-radius: 5px;
  display: flex;
	justify-content: space-between;
	border: 2px solid rgb(34, 2, 243);
	align-items: center;
}
.btn {
  border: 2px solid rgb(233, 33, 39);
  color: rgb(233, 33, 39);

  &:hover {
    background: rgb(233, 33, 39);
  }
}
</style>
