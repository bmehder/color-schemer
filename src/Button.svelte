<script>
	import { toProperCase } from './utils'
	
	export let text
</script>

<button on:click>
	{toProperCase(text)}
</button>

<style>
	button {
		align-self: end;
		padding: 0.2rem 1rem;
	}
</style>