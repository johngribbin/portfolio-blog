<script>
  import { layout, isActive, url, goto, page } from "@sveltech/routify";
  export let node = $layout;

  console.log(node);
</script>

<style>
  nav {
    display: flex;
  }

  nav a {
    margin-right: 1em;
  }

  .active {
    text-decoration: underline;
  }
</style>

<nav>
  {#each node.children as node}
    <a href={$url(node.path)} class:active={$isActive(node.path)}>
      {node.title}
    </a>
    {#if node.children.length}
      <svelte:self {node} />
    {/if}
  {/each}
</nav>
