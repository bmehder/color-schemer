<script>
  import { randomHex } from './utils'
  import Icon from '@iconify/svelte'

  import ColorInput from './ColorInput.svelte'
  import Select from './Select.svelte'
  import Button from './Button.svelte'

  export let hexColor
  export let schemes
  export let scheme
  export let variations
  export let variation

  const setRandomColor = () => (hexColor = randomHex())
</script>

<header>
  <h1 class="flex-center">Color Schemer <Icon icon="mdi:color" /></h1>
  <div class="flex-center">
    <ColorInput label="color" bind:hexColor />
    <Select label="scheme" options={schemes} bind:option={scheme} />
    <Select label="variation" options={variations} bind:option={variation} />
    <Button text="random" on:click={setRandomColor} />
  </div>
</header>

<style>
  header {
    display: grid;
    gap: 1rem;
  }
</style>