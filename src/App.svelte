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

  .footer {
    bottom: 0;
    position: fixed;
  }
</style>

<main>
  <Nav />

  <section>
    {#if $skill === 'music'}
      <Music />
    {:else if $skill === 'code'}
      <Code />
    {:else if $skill === 'words'}
      <Words />
    {/if}
  </section>

  <section class="footer">
    <h2>johngribbin @ protonmail.com</h2>
  </section>
</main>
