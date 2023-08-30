<script>
	export let text
</script>

<button on:click>
	{text[0].toUpperCase() + text.slice(1)}
</button>

<style>
	button {
		align-self: end;
		padding: 0.2rem 1rem;
	}
</style>