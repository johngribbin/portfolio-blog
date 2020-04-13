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
    border: 1px solid black;
  }

  .footer {
    border: 3px dotted black;
    bottom: 0;
    padding: 1em;
    position: fixed;
    margin-bottom: 1em;
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
