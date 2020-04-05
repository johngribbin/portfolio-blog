<script>
  import Tiles from "./Tiles.svelte";
  import Music from "./Music.svelte";

  let src = "./images/pattern28.jpg";

  let showMusic = false;
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

  <Tiles />
  {#if showMusic}
    <Music />
  {/if}
</main>
