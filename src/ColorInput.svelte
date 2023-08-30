<script>
	import { toProperCase } from './utils'

	export let label
	export let hexColor
</script>

<div class="input-group">
	<label for="{label}">{toProperCase(label)}</label>
	<input id="{label}" type="color" name="{label}" bind:value={hexColor} />
</div>