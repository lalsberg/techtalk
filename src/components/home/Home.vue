<template>
	<div>
		<input type="search" class="filter" placeholder="Filter solutions" v-on:input="filter = $event.target.value">
		{{ filter }}

		<div class="solution-panel" v-for="solution in filteredSolutions">
			<the-solution :solution="solution"/>
		</div>
	</div>
</template>


<script>
	import Solution from '../../components/Solution.vue';

	export default {
		name: 'home',

	    components: {
	        'the-solution': Solution
	    },

		data () {
			return {
				solutions: [],
				filter: ''
			}
		},

		computed: {
			filteredSolutions() {
				if (!this.filter) {
					return this.solutions;
				}
				let exp = new RegExp(this.filter.trim(), 'i');
				return this.solutions.filter(solution => exp.test(solution.title));
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

	.filter {
		display: block;
		width: 100%;
	}
</style>
