<template>
	<div id="app">
		<Header></Header>
		<Pixabay/>
	</div>
</template>

<script>
import Pixabay from '@/components/Pixabay';
import Header from '@/components/Header';

export default {
	name: 'App',
	components: {
		Pixabay,
		Header
	}
}
</script>

<style lang="scss">

</style>
