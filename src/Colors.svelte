<script>
  import { hexToHSL } from './utils'
  import Color from './Color.svelte'

  export let hexColors
  export let hexColor

  $: [hue, sat, light] = hexToHSL(hexColor)
</script>

<main>
  <Color {hexColor} --hue={hue} --sat={sat} --light={light} />
  {#each hexColors as hexValue}
    {@const hexColor = '#' + hexValue}
    {@const [hue, sat, light] = hexToHSL(hexColor)}
    <Color {hexColor} --hue={hue} --sat={sat} --light={light} />
  {/each}
</main>

<style>
  main {
    display: grid;
    align-self: self-start;
    gap: 1rem;
    margin-block-start: 0.5rem;
  }
</style>
