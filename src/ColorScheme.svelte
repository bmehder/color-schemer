<script>
  import Icon from '@iconify/svelte'

  let darkMode = 'dark'

  const toggleDarkMode = () => (darkMode = darkMode === 'dark' ? 'light' : 'dark')

  $: document.querySelector('html').style.colorScheme = darkMode
</script>

<button class="unset" on:click={toggleDarkMode}>
  {#if darkMode === 'dark'}
    <Icon icon="ic:outline-dark-mode" width="32" />
  {:else}
    <Icon icon="ic:baseline-dark-mode" width="32" />
  {/if}
</button>