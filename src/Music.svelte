<script>
  let playlists = [
    "https://open.spotify.com/embed/artist/6lqOL0LrdugmRcz6fPE3IF",
    "https://open.spotify.com/embed/artist/4AxGcwEQdFCy1MlkyYgZ6y"
  ];
</script>

<style>
  h2 {
    margin-bottom: 1em;
  }

  p {
    margin-bottom: 1em;
  }
</style>

<section>
  <h2>Music here</h2>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
    quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
    consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
    cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
    non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
  </p>
  {#each playlists as playlist}
    <iframe
      title="spotify playlist"
      src={playlist}
      width="300"
      height="380"
      frameborder="0"
      allowtransparency="true"
      allow="encrypted-media" />
  {/each}

</section>
