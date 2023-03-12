<template>
  <div>
    <input :value="modelValue" @input="updateInput" type="text" />
  </div>
</template>

<script>
export default {
  name: 'custom-input',
  props: {
    modelValue: {
      type: [String, Number],
      required: true,
    },
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value);
    },
  },
};
</script>

<style lang="scss" scoped>
input {
  padding: 10px 20px;
  font-size: 18px;
  border: 2px solid rgb(33, 84, 214);
  border-radius: 3px;
  outline: none;
}
</style>
