<template>
  <div class="dialog" v-if="show" @click="hideDialog">
    <div @click.stop class="dialog__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'custom-dialog',
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
	methods: {
		hideDialog() {
			this.$emit('update:show', false)
		}
	}
};
</script>

<style lang="scss" scoped>
.dialog {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  position: fixed;
  background: #00000084;
  display: flex;

  &__content {
    padding: 20px;
    min-width: 200px;
    min-height: 100px;
    margin: auto;
    background: #fff;
    border-radius: 10px;
  }
}
</style>
