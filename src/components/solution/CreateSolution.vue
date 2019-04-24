<template>
	<div class="wrapper">
		<label>Titulo</label>
		<input v-model="solution.title" class="my-input"></input>

		<label>Descricao</label>
		<textarea v-model="solution.description" class="my-input"></textarea>

		<my-button @buttonClicked='register()'>
			<span>Register</span>
		</my-button>

	</div>
</template>


<script>
	import TButton from '../shared/TButton.vue';

	export default {

	    components: {
	        'my-button': TButton
	    },

		data () {
			return {
				solution: {
					title: '',
					description: ''
				}
			}
		},

		methods: {
			register: function() {
				this.$http.post('http://localhost:8080/resolution/create', this.solution)
					.then(res => res.json())
					.then(function(response) {
						console.log(response);
					}
					, err => {this.sending = false; console.log(err)});
			}
		}
	}
</script>


<style>
	.wrapper {
		width: 40%;
		margin: 0 auto;
	}
	.my-input {
		display: block;
		margin: 10px 0px;
	}

	input {
		width: 100%;
	}
	textarea {
		width: 100%;
		height: 500px;
	}
</style>
