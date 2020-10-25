<template>
	<div class="Pixabay">
		<PixabaySearch @searchResult="getSearchResult"/>
		<PixabayResult v-bind:resultJson="resultJson"/>
	</div>
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

<style scoped>

</style>
