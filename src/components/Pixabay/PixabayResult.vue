<template>
	<div class="PixabayResult">
		<div class="PixabayResult__loop" v-for="picture of resultJson.hits" :key="picture.id">
			<Picture v-bind:picture="picture"/>
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
.PixabayResult {
	display: flex;
	flex-wrap: wrap;
	&__loop {

	}
}
</style>
