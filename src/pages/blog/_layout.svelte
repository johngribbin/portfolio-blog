<script>
  import Nav from "./_nav.svelte";
</script>

<style>
  div {
    display: flex;
  }

  aside {
    margin-left: 1em;
  }
</style>

<div>
  <Nav />
  <aside>
    <slot />
  </aside>
</div>
