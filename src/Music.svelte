<script>
  let playlists = [
    "https://open.spotify.com/embed/artist/6lqOL0LrdugmRcz6fPE3IF",
    "https://open.spotify.com/embed/artist/4AxGcwEQdFCy1MlkyYgZ6y"
  ];
</script>

<style>

</style>

<section>
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
