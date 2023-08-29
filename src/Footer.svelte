<script>
	import Icon from '@iconify/svelte';

	export let label
	export let url
</script>

<footer>
	<p>Powered by <a href="{url}" target="_blank">{label}</a></p>
	<div class="icon">
		<a href="https://github.com/bmehder/color-schemer" target="_blank">
			<Icon icon="icon-park:github" width='32' style="color: red"/>
		</a>
	</div>
</footer>

<style>
	footer {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}
	.icon {
		display: grid;
		place-items: center;
		line-height: 0;
		aspect-ratio: 1;
		padding: 0.125em;
		background-color: white;
		border-radius: 50%;
	}
</style>