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

  ul {
    padding-left: 1em;
  }

  li {
    list-style-type: square;
    margin-bottom: 1em;
  }
</style>

<section>
  <h2>
    I started releasing music in 2011 under the pseudonym Building Pictures.
    This project helped me to move from Northern Ireland to the United States.
    In more recent years I have been releasing music with my friend Aaron for
    our band Tamper.
  </h2>

  <section>
    <ul>
      <li>
        <a
          href="https://buildingpictures.bandcamp.com/album/training-up-my-soul"
          target="_blank"
          rel="noopener noreferrer">
          2011 - Training Up My Soul (EP)
        </a>
      </li>
      <li>
        <a
          href="https://open.spotify.com/album/39EKHOTWE3qSYZkAhv4K0D"
          target="_blank"
          rel="noopener noreferrer">
          2013 - West Orchard (album)
        </a>
      </li>
      <li>
        <a
          href="https://open.spotify.com/album/04GctAOVjACcWuTKzOBjpt"
          target="_blank"
          rel="noopener noreferrer">
          2013 - Tamper (EP)
        </a>
      </li>
      <li>
        <a
          href="https://open.spotify.com/album/6clNFyBH1taw3nFJHQXdYT"
          target="_blank"
          rel="noopener noreferrer">
          2016 - Bought and Sold (EP)
        </a>
      </li>
      <li>
        <a
          href="https://open.spotify.com/album/2uxh36EwPTf0UBdmzeyz88"
          target="_blank"
          rel="noopener noreferrer">
          2017 - Eagle Bridge (EP)
        </a>
      </li>
      <li>
        <a href="#">Tamper debut album coming soon...</a>
      </li>
    </ul>

  </section>

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
