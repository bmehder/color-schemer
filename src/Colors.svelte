<script>
  import { hexToHSL } from './utils'
  import Color from './Color.svelte'

  export let hexColors
  export let hexColor

  $: [hue, sat, light] = hexToHSL(hexColor)
</script>

<main class="grid">
  <Color {hexColor} --hue={hue} --sat={sat} --light={light} />
  <div class="grid">
    {#each hexColors as hexValue}
      {@const hexColor = '#' + hexValue}
      {@const [hue, sat, light] = hexToHSL(hexColor)}
      <Color {hexColor} --hue={hue} --sat={sat} --light={light} />
    {/each}
  </div>
</main>

<style>
  main {
    grid-template-columns: repeat(auto-fit, minmax(12em, 1fr));
  }
</style>
