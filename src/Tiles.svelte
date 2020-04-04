<script>
  let tiles = [
    { title: "Code", background: "./images/pattern28.jpg" },
    { title: "Music", background: "./images/pattern49.jpg" },
    { title: "Words", background: "./images/pattern47.jpg" }
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
</style>

<section>
  {#each tiles as tile}
    <a href="https://github.com/johngribbin">
      <div>
        <h2>{tile.title.toUpperCase()}</h2>
        <img src={tile.background} alt="background" />
      </div>
    </a>
  {/each}
</section>
