<script>
  import { onDestroy } from "svelte";
  import { skill } from "./stores.js";
  import Nav from "./Nav.svelte";
  import Socials from "./Socials.svelte";
  import Code from "./Code.svelte";
  import Music from "./Music.svelte";
  import Words from "./Words.svelte";
</script>

<style>
  main {
    margin: 4em auto;
    max-width: 1200px;
  }

  .copy {
    margin-bottom: 6em;
    max-width: 600px;
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
      padding: 0em 2em 0em 2em;
    }
  }
</style>

<main>
  <!-- <Nav /> -->
  <div class="copy">
    <p>
      Inspired by the Bitcoin whitepaper I decided it was time to learn to code.
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
