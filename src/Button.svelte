<script>
	import { toProperCase } from './utils'
	
	export let text
</script>

<div class="input-group">
	<label for="">-</label>
	<button on:click>
		{toProperCase(text)}
	</button>
</div>

<style>
	label {
		opacity: 0;
	}
	button {
		padding: 0.25rem 1rem;
	}
</style>