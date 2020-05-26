<script>
  import { Router } from "@sveltech/routify";
  import { routes } from "@sveltech/routify/tmp/routes";
  import { onMount } from "svelte";
  import { fade } from "svelte/transition";
  import Socials from "../Socials.svelte";
  import Code from "../Code.svelte";

  let visible = false;

  onMount(() => {
    visible = true;
  });
</script>

<style>
  .copy {
    margin-top: 5em;
    width: 50%;
  }

  h2 {
    margin: 0.75em 0;
  }

  a {
    text-decoration: underline;
  }

  /* Tablet */
  @media (max-width: 1000px) {
    .copy {
      width: 100%;
    }
  }
</style>

{#if visible}
  <div transition:fade={{ delay: 250, duration: 300 }} class="copy">
    <h1>Hey, Im John.</h1>
    <h2>
      I am a front-end developer with a passion for all things open-source,
      Bitcoin and Ethereum. I also make
      <a
        href="https://soundcloud.com/tampermusic"
        target="_blank"
        rel="noopener noreferrer">
        music.
      </a>

    </h2>
    <Socials />
  </div>
{/if}
<Code />
