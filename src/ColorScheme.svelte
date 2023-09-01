<script>
  import Icon from '@iconify/svelte'

  let colorScheme = 'dark'

  const toggleColorScheme = () => (colorScheme = colorScheme === 'dark' ? 'light' : 'dark')

  $: document.querySelector('html').style.colorScheme = colorScheme
</script>

<button class="unset" on:click={toggleColorScheme}>
  {#if colorScheme === 'dark'}
    <Icon icon="ic:outline-dark-mode" width="32" />
  {:else}
    <Icon icon="ic:baseline-dark-mode" width="32" />
  {/if}
</button>