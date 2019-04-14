<template>
	<div id="app">
		<div class="solution-panel" v-for="solution in solutions">
			{{ solution.description }}
		</div>
	</div>
</template>

<script>
export default {
	name: 'app',
	data () {
		return {
			solutions: []
		}
	},

	created() {
		this.$http.get('http://localhost:8080/resolutions')
      		.then(res => res.json())
      		.then(solutions => this.solutions = solutions, err => console.log(err));
	}
}
</script>

<style>
	h1 {
		font-weight: normal;
	}
</style>
