<template>
	<button class="btn">
		<slot></slot>
	</button>
</template>

<script>
export default {
	name: 'custom-button'
}
</script>

<style lang="scss" >

.btn {
	padding: 10px 20px; 
	border-radius: 5px;
	background: none;
	font-size: 18px;
	transition: 0.15s ease-in-out;
	cursor: pointer;
	color: blue;
  border: 2px solid blue;

	&:hover {
		color: aliceblue;
		background: blue;
	}
}
</style>