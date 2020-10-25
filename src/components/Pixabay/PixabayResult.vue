<template>
	<div class="PixabayResult is-flex is-flex-wrap-wrap is-justify-content-center">
		<div class="PixabayResult__loop card m-1" v-for="picture of resultJson.hits" :key="picture.id">
			<div class="card-content">
				<Picture v-bind:picture="picture"/>
			</div>
		</div>
	</div>
</template>

<script>
import Picture from '@/components/Pixabay/Picture/Picture';

export default {
	name: 'PixabayResult',
	components: {
		Picture
	},
	props: {
		resultJson: Object
	},
	created() {
	},
}
</script>

<style lang="scss" scoped>
</style>
