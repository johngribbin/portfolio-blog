<script>
  import { onDestroy } from "svelte";
  import { skill } from "./stores.js";
  import Nav from "./Nav.svelte";
  import Code from "./Code.svelte";
  import Music from "./Music.svelte";
  import Words from "./Words.svelte";
</script>

<style>
  main {
    margin: 0 auto;
    max-width: 1200px;
    padding: 1em;
  }

  section {
    border: 3px dotted black;
    padding: 1em;
    margin-bottom: 2em;
  }
</style>

<main>
  <section>
    <h2>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
      veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
      commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
      velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
      cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id
      est laborum.
    </h2>
    <h2>johngribbin @ protonmail.com</h2>
  </section>

  <Nav />

  {#if $skill === 'music'}
    <Music />
  {:else if $skill === 'code'}
    <Code />
  {:else if $skill === 'words'}
    <Words />
  {/if}

</main>
