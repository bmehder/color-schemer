<script>
  import { toProperCase } from './utils'

  export let label
  export let distance
</script>

<div class="input-group">
  <label for={label}>{toProperCase(label)}</label>
  <input type="range" id={label} min="0.1" max="1" step="0.1" bind:value={distance} />
</div>
