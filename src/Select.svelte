<script>
	import { toProperCase } from './utils'

	export let options
	export let option
	export let label
</script>

<div class="input-group">
	<label for="{label}">{toProperCase(label)}</label>
	<select id="{label}" name="{label}" bind:value={option}>
		{#each options as _option}
			<option value="{_option}">{toProperCase(_option)}</option>
		{/each}
	</select>
</div>
