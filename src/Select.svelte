<script>
	export let options
	export let option
	export let label
</script>

<div class="input-group">
	<label for="{label}">{label[0].toUpperCase() + label.slice(1)}</label>
	<select name="{label}" bind:value={option}>
		{#each options as _option}
			<option>{_option}</option>
		{/each}
	</select>
</div>

<style>
	select {
		padding: 0.25rem;
	}
</style>