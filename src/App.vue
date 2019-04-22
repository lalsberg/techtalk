<template>
	<div>
		<input type="text" v-on:input="texto = $event.target.value">

		{{ texto }}
	</div>
</template>


<script>
	export default {
		data () {
			return {
				texto: ''
			}
		},
	}
</script>


<style>
</style>
