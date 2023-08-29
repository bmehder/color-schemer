<script>
	export let label
	export let hexColor
</script>

<div class="input-group">
	<label for="{label}">{label[0].toUpperCase() + label.slice(1)}</label>
	<input type="color" name="{label}" bind:value={hexColor} />
</div>