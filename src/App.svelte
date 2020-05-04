<script>
  import { onMount } from "svelte";
  import { slide } from "svelte/transition";
  import { quintOut } from "svelte/easing";
  import { skill } from "./stores.js";
  import Socials from "./Socials.svelte";
  import Code from "./Code.svelte";
  import Music from "./Music.svelte";
  import Words from "./Words.svelte";

  let visible = false;

  onMount(() => {
    visible = true;
  });
</script>

<style>
  main {
    margin: 4em auto;
    max-width: 1150px;
  }

  .copy {
    margin-bottom: 6em;
    max-width: 550px;
  }

  h2 {
    margin-bottom: 1em;
  }

  @media (max-width: 600px) {
    main {
      margin-top: 2em;
    }

    .copy {
      padding: 0em 1em 0em 1em;
    }
  }
</style>

<main>
  {#if visible}
    <div transition:slide={{ delay: 250, duration: 300 }} class="copy">
      <h2>Hey, Im John.</h2>
      <h2>
        I am a front-end developer with a passion for all things open-source and
        Bitcoin. I'm framework agnostic but my personal favorites are React and
        Svelte.
      </h2>
      <Socials />
    </div>
  {/if}

  <section>
    <!-- {#if $skill === 'music'}
      <Music /> -->
    <!-- {:else if $skill === 'code'} -->
    <Code />
    <!-- {:else if $skill === 'words'}
      <Words />
    {/if} -->
  </section>

</main>
