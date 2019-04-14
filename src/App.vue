<template>
	<div id="app">
		<div class="solution-panel" v-for="solution in solutions">
			{{ solution.title }}
		</div>
	</div>
</template>

<script>
export default {
	name: 'app',
	data () {
		return {
			solutions: [
				{
					title: 'solution 1',
					description: 'description 1',
				},
				{
					title: 'solution 2',
					description: 'description 2',
				},
			]
		}
	}
}
</script>

<style>
	h1 {
		font-weight: normal;
	}
</style>
