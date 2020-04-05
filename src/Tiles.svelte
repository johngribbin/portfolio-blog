<script>
  let tiles = [
    {
      title: "Code",
      imgSrc: "./images/pattern28.jpg",
      url: "https://github.com/johngribbin",
      selected: true
    },
    {
      title: "Music",
      imgSrc: "./images/pattern49.jpg",
      url: "https://soundcloud.com/tampermusic",
      selected: false
    },
    {
      title: "Words",
      imgSrc: "./images/pattern47.jpg",
      url: "https://medium.com/@johnggribbin",
      selected: false
    }
  ];
</script>

<style>
  section {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    margin-bottom: 2em;
  }

  a {
    color: black;
  }

  div {
    border: 3px dotted transparent;
    margin: 1em;
    max-width: 350px;
    position: relative;
  }

  div:hover {
    border: 3px dotted black;
    border-radius: 10px;
    cursor: pointer;
  }

  h2 {
    background: white;
    border-radius: 0px 0px 15px 0px;
    position: absolute;
    margin: 0;
    padding: 0.25em 0.5em 0.25em 0.25em;
  }

  img {
    border-radius: 10px;
    display: block;
    height: auto;
    width: 300px;
  }

  img:hover {
    opacity: 0.2;
  }

  .water {
    border: 1pc solid red;
  }
</style>

<section>
  {#each tiles as tile}
    <div>
      <h2>{tile.title.toUpperCase()}</h2>
      <img src={tile.imgSrc} alt="background" on:click{} />
    </div>
  {/each}
  {#each tiles as tile}
    {#if tile.selected === true}
      <p>{tile.title} is chosen</p>
    {/if}
  {/each}
</section>
