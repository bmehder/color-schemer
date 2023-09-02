<script>
  import { randomHex } from './utils'
  import ColorScheme from './ColorScheme.svelte'
  import ColorInput from './ColorInput.svelte'
  import Select from './Select.svelte'
  import Range from './Range.svelte'
  import Button from './Button.svelte'

  export let hexColor
  export let schemes
  export let scheme
  export let variations
  export let variation
  export let distance

  const setRandomColor = () => (hexColor = randomHex())
</script>

<header class="grid">
  <h1 class="flex-center">Color Schemer <ColorScheme /></h1>
  <div class="flex-center">
    <ColorInput label="color" bind:hexColor />
    <Select label="scheme" options={schemes} bind:option={scheme} />
    {#if scheme === 'triade' || scheme === 'tetrade' || scheme === 'analogic'}
      <Range label="distance" bind:distance />
    {/if}
    <Select label="variation" options={variations} bind:option={variation} />
    <Button text="random" on:click={setRandomColor} />
  </div>
</header>

<style>
  header {
    padding-block-start: 2rem;
  }
  .flex-center {
    align-items: start;
  }
</style>