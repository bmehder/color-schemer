<script>
	import Icon from '@iconify/svelte';

	export let label
	export let url
</script>

<footer>
	<p>Powered by <a href="{url}" target="_blank">{label}</a></p>
	<Icon icon="icon-park:github" width='32'/>
</footer>

<style>
	footer {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
		/* padding-block: 1rem; */
		/* text-align: center; */
	}
</style>