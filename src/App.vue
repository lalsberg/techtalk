<template>
	<div>

		<nav>
			<ul>

				<!-- a faz o reload da pagina -->
				<!-- <li><a href="/">Home</a></li>
				<li><a href="/createSolution">Create Solution</a></li> -->

				<!-- <li><router-link to="/">Home</router-link></li>
				<li><router-link to="/createSolution">Create Solution</router-link></li> -->

				<li v-for="route in routes">
					<router-link :to="route.path ? route.path : '/'">{{route.theTitle}}</router-link>
				</li>
			</ul>
		</nav>

		<router-view></router-view>

	</div>
</template>


<script>
import { routes }  from './routes';

	export default {
		data () {
			return {
				routes
			}
		},
	}
</script>


<style>
</style>
