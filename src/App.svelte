<script>
  import { onMount } from "svelte";
  import { slide } from "svelte/transition";
  import { quintOut } from "svelte/easing";
  import Socials from "./Socials.svelte";
  import Code from "./Code.svelte";

  let visible = false;

  onMount(() => {
    visible = true;
  });
</script>

<style>
  main {
    max-width: 1200px;
    margin: 4em auto;
    padding: 0 2em;
  }

  .copy {
    width: 50%;
  }

  h2 {
    margin: 0.75em 0;
  }

  a {
    text-decoration: underline;
  }

  footer {
    margin-top: 10em;
    text-align: center;
  }

  /* Tablet */
  @media (max-width: 1000px) {
    main {
      max-width: 800px;
    }

    .copy {
      width: 100%;
    }
  }

  /* Phone */
  @media (max-width: 400px) {
    main {
      padding: 0 1em;
    }
  }
</style>

<main>
  {#if visible}
    <div transition:slide={{ delay: 250, duration: 300 }} class="copy">
      <h1>Hey, Im John.</h1>
      <h2>
        I am a front-end developer with a passion for all things open-source and
        Bitcoin. I also make
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
  <footer>
    <a href="https://github.com/johngribbin/portfolio_2020">
      This website is open-source
    </a>
  </footer>
</main>
