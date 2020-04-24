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
        Hey, Im John. I write code and
        <a
          href="https://open.spotify.com/artist/6lqOL0LrdugmRcz6fPE3IF"
          target="_blank"
          rel="noopener noreferrer">
          tunes.
        </a>
      </p>

      <p>
        I lead all front-end development for the
        <a
          href="https://consensys.space"
          target="_blank"
          rel="noopener noreferrer">
          Space
        </a>
        team at
        <a
          href="https://consensys.net"
          target="_blank"
          rel="noopener noreferrer">
          ConsenSys.
        </a>
        We build awesome open-source collaboration platforms to diversify,
        democratize, and decentralize space endeavors.
      </p>
      <p>
        I'm framework agnostic but my personal favorites are React and Svelte.
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
