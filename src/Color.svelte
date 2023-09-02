<script>
  import Icon from '@iconify/svelte'
  import { fade } from 'svelte/transition'
  import { wait } from './utils'

  export let hexColor

  let isCopied = false
  let isHidden = false

  const copyText = evt => navigator.clipboard.writeText(evt.target.innerHTML.trim())
  const hide = () => (isHidden = true)

  async function copyToClipboard(evt) {
    copyText(evt)
    isCopied = true
    await wait(2000)
    isCopied = false
  }
</script>

{#if !isHidden}
  <button class="auto-color" on:click={copyToClipboard}>
    {#if isCopied}
      <span in:fade>Hex Code Copied!</span>
    {:else}
      {hexColor}
    {/if}
  </button>
{/if}

<style>
  button {
    all: unset;
    padding-block: 1rem;
    background-color: hsl(var(--hue), calc(var(--sat) * 1%), calc(var(--light) * 1%));
    font-family: 'Menlo', monospace;
    text-align: center;
    text-transform: uppercase;
    cursor: pointer;
    border-radius: 0.125rem;
  }
  button:focus {
    outline: 1px solid white;
  }
  .auto-color {
    --threshold: 50;
    --switch: calc((var(--light) - var(--threshold)) * -100%);
    color: hsl(0, 0%, var(--switch));
  }
</style>
