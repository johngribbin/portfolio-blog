<script>
  import { layout, isActive, url, goto, page } from "@sveltech/routify";
  export let node = $layout;

  function tidyTitle(title) {
    return title.substring(3).replace(/_/g, " ");
  }
</script>

<style>
  nav {
    display: flex;
    margin-bottom: 5em;
  }

  a {
    margin-right: 1em;
  }

  a:hover {
    text-decoration: underline;
  }

  .active {
    color: rgba(14, 237, 207, 0.8);
    text-decoration: underline;
    text-decoration-color: rgba(14, 237, 207, 0.8);
  }
</style>

<nav>
  {#each node.children as node}
    {#if node.title !== 'blog'}
      <a href={$url(node.path)} class:active={$isActive(node.path)}>
        {tidyTitle(node.title)}
      </a>
    {/if}
    <!-- 
      For nested directories in the 'blog' directory
      {#if node.children.length}
      <svelte:self {node} />
    {/if} -->
  {/each}
</nav>
