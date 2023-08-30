<script>
  import Icon from '@iconify/svelte'
  import { hexToHSL, randomHex } from './utils'
  import ColorScheme from 'color-scheme'
  import ColorInput from './ColorInput.svelte'
  import Select from './Select.svelte'
  import Button from './Button.svelte'
  import Swatch from './Swatch.svelte'

  const schemes = ['contrast', 'analogic', 'triade', 'tetrade', 'mono']
  const variations = ['default', 'pastel', 'hard', 'soft', 'light', 'pale']

  let scheme = schemes.at(0)
  let variation = variations.at(0)
  let hexColor = randomHex()
  $: [hue, sat, light] = hexToHSL(hexColor)

  $: hexColors = new ColorScheme()
    .from_hex(hexColor.slice(1))
    .scheme(scheme)
    .variation(variation)
    .colors()

  const setRandomColor = () => (hexColor = randomHex())
</script>

<div class="wrapper">
  <h1>Color Schemer</h1>
  <header class="flex-center">
    <ColorInput label="color" bind:hexColor />
    <Select label="scheme" options={schemes} bind:option={scheme} />
    <Select label="variation" options={variations} bind:option={variation} />
    <Button text="random" on:click={setRandomColor} />
  </header>

  <main>
    <Swatch {hexColor} --hue={hue} --sat={sat} --light={light} />
    {#each hexColors as hexValue}
      {@const hexColor = '#' + hexValue}
      {@const [hue, sat, light] = hexToHSL(hexColor)}
      <Swatch {hexColor} --hue={hue} --sat={sat} --light={light} />
    {/each}
  </main>

  <footer class="flex-center">
    <p>
      Powered by <a href="https://github.com/c0bra/color-scheme-js" target="_blank"
        >color-scheme-js</a
      >
    </p>
    <div class="icon">
      <a href="https://github.com/bmehder/color-schemer" target="_blank">
        <Icon icon="icon-park:github" width="32" />
      </a>
    </div>
  </footer>
</div>

<style>
  main {
    display: grid;
    align-self: self-start;
    gap: 1rem;
    margin-block-start: 0.5rem;
  }
</style>
