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

  p {
    font-size: 18px;
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
      <p>
        Inspired by the Bitcoin whitepaper I decided it was time to learn to
        code.
      </p>

      <p>
        Currently I lead all front-end development at
        <a
          href="https://consensys.space"
          target="_blank"
          rel="noopener noreferrer">
          ConsenSys Space.
        </a>
        We build awesome open-source collaboration platforms to diversify,
        democratize, and decentralize space endeavors.
      </p>
      <p>
        Although I am framework agnostic, my personal favorites are React and
        Svelte.
      </p>

      <Socials />
    </div>
  {/if}

  <section>
    {#if $skill === 'music'}
      <Music />
    {:else if $skill === 'code'}
      <Code />
    {:else if $skill === 'words'}
      <Words />
    {/if}
  </section>

</main>
