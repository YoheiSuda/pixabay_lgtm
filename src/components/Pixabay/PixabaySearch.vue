<template>
	<div class="PixabaySearch field has-addons">
		<div class="control">
			<input class="input" v-model="searchKey" name="key" type="text" placeholder="e.g.)flower">
		</div>
		<div class="control">
			<button class="button is-info" v-on:click="searchPicture">Search</button>
		</div>
	</div>
</template>

<script>
export default {
	name: 'PixabaySearch',
	data() {
		return {
			searchKey: ''
		}
	},
	created() {
		this.searchPicture();
	},

	methods: {
		searchPicture: function () {
			let _this = this;
			fetch(this.createURL(this.searchKey))
				.then(function (data) {
					return data.json();
				})
				.then(function (json) {
					_this.$emit('searchResult', json);
				})
		},
		createURL: function (key) {
			const baseUrl = 'https://pixabay.com/api/?key=11958254-482d8ff0de6c1a2ed9602b353';
			let keyWord = '&q=' + encodeURIComponent(key);
			const option = '&safesearch=true&per_page=40';
			let url = baseUrl + keyWord + option;

			return url;
		},
	}
}
</script>

<style lang="scss" scoped>
.PixabaySearch {
	input {

	}

}
</style>
