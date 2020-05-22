<script>
  import { isActive } from "@sveltech/routify";
</script>

<style>
  main {
    max-width: 1200px;
    margin: 4em auto;
    padding: 0 2em;
  }

  nav {
    border-bottom: 1px solid rgba(14, 237, 207, 0.3);
    display: flex;
    margin-bottom: 5em;
    padding-bottom: 0.5em;
    font-size: 18px;
    font-weight: 300;
    line-height: 1.4;
  }

  a {
    margin-right: 2em;
  }

  .active {
    color: rgba(14, 237, 207, 0.8);
    text-decoration: underline;
    text-decoration-color: rgba(14, 237, 207, 0.8);
  }

  /* Tablet */
  @media (max-width: 1000px) {
    main {
      max-width: 800px;
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
  <nav>
    <a href={'/'} class:active={$isActive('./index')}>Home</a>
    <a
      href={'/blog/01_my_first_post'}
      class:active={$isActive('/blog/01_my_first_post')}>
      Blog
    </a>
  </nav>
  <slot />
</main>
