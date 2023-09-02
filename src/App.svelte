<script>
  import { randomHex } from './utils'
  import ColorScheme from 'color-scheme'
  import Header from './Header.svelte'
  import Colors from './Colors.svelte'
  import Footer from './Footer.svelte'

  const SCHEMES = Object.freeze(['contrast', 'analogic', 'triade', 'tetrade', 'mono'])
  const VARIATIONS = Object.freeze(['default', 'pastel', 'hard', 'soft', 'light', 'pale'])

  let hexColor = randomHex()
  let scheme = SCHEMES.at(0)
  let variation = VARIATIONS.at(0)

  $: hexColors = new ColorScheme()
    .from_hex(hexColor.slice(1))
    .scheme(scheme)
    .variation(variation)
    .colors()
</script>

<div class="wrapper">
  <Header
    schemes={SCHEMES}
    variations={VARIATIONS}
    bind:hexColor
    bind:scheme
    bind:variation
  />

  <Colors {hexColors} {hexColor} />

  <Footer />
</div>

<style>
  .wrapper {
    min-height: 100dvh;
    display: grid;
    grid-template-rows: auto 1fr auto;
    gap: 2em;
    width: min(100% - 1.5rem, 80%);
    max-width: 48em;
    margin-inline: auto;
    padding-block: 1.5rem;
    text-align: center;
  }
</style>
