<template>
	<div class="Picture">
		<img v-bind:src="picture.previewURL">
	</div>
</template>

<script>
export default {
	name: 'Picture',
	props: {
		picture: Object
	}
}
</script>

<style scoped>

</style>
