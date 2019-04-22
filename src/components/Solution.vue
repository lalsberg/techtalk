<template>
	<div class="solution">

		<div class="solution-head">
			<span> {{ solution.title }}</span>
		</div>

		<div class="solution-description">
			<p><span><pre>{{ solution.description }}</pre></span></p>
		</div>

		<div class="frequency">
			<p class="mg-font-bold total-value-desc">Frequência:</p>
			<p class="mg-font-bold mg-font-size-xl real-value"> {{ solution.frequency }} </p>
		</div>

	</div>
</template>

<script>
export default {
	name: 'Solution',

    props: {
        solution: {
            required: true
        }
    }
}
</script>

<style>
	.frequency {
	    padding: 10px;
	    margin-top: 10px;
	    border-top: 1px solid silver;
	}

	p {
	    -webkit-margin-before: 0;
	    -webkit-margin-after: 0;
	    -webkit-margin-start: 0;
	    -webkit-margin-end: 0;
	}

	.mg-font-size-xl {
	    font-size: 1.5rem;
	}

	pre {
		overflow-x: auto;
		white-space: pre-wrap;
		white-space: -moz-pre-wrap;
		white-space: -pre-wrap;
		white-space: -o-pre-wrap;
		word-wrap: break-word;
	}

	.solution-head {
		color: rgb(51, 51, 51);
		background-color: rgb(245, 245, 245);
	    border-color: rgb(221, 221, 221);
	    border-top-left-radius: 6px;
	    border-top-right-radius: 6px;
	    padding: 10px 15px;
	    border-bottom: 1px solid silver;
	}

	.solution {
	    font-family: helvetica_neue_lt_std45_light,sans-serif;
	    color: #555;
	}

	.solution-description li {		
		display: list-item;
		text-align: -webkit-match-parent;
		margin: 50px 0;
	}

	.solution {
		width: 90%;
		border: 1px solid silver;
    	border-radius: .4rem;
    	margin: 10px 0;
    	margin-left: auto;
		margin-right: auto;
		margin-top: 1em;
	}

	@media (min-width: 1024px) {
		.solution {
			width: 40%;
		}
	}

	.total-value-desc {
		display: inline-block;
	}
	.real-value {
		display: inline-block;
	}

	.solution-description {
		padding: 0 1.4rem;
		list-style-type: none;
	}

	.solution-description span, .frequency {
		font-family: Roboto,Noto Sans,-apple-system,BlinkMacSystemFont,sans-serif;
	}

	.mg-font-bold {
	    font-weight: 400;;
	}

	.mg-font-size-sm {
		font-size: 1.2rem;
	}
</style>
