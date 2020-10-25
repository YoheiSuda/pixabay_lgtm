<template>
	<section class="section Pixabay">
		<div class="container">
			<PixabaySearch @searchResult="getSearchResult"/>
			<PixabayResult v-bind:resultJson="resultJson"/>
		</div>
	</section>
</template>

<script>
import PixabaySearch from '@/components/Pixabay/PixabaySearch';
import PixabayResult from '@/components/Pixabay/PixabayResult';

export default {
	name: 'Pixabay',
	data() {
		return {
			resultJson: {}
		}
	},
	components: {
		PixabaySearch,
		PixabayResult
	},
	methods: {
		getSearchResult: function (json) {
			this.resultJson = json;
		}
	}
}
</script>

<style lang="scss" scoped>
</style>
