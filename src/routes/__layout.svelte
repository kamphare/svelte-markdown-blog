<script context="module">
  export const load = ({ url }) => {
    const currentRoute = url.pathname

    return {
      props: {
        currentRoute
      }
    }
  }
</script>

<script>
  import Header from '$lib/components/Header.svelte'
  import '$lib/css/styles.scss'
  import { fade } from 'svelte/transition'

export let currentRoute
</script>

<Header />

{#key currentRoute}
  <main in:fade={{ duration: 300, delay: 150 }} out:fade={{ duration: 150 }}>
    <slot />
  </main>
{/key}

<footer>👣 You guessed it 👣</footer>
