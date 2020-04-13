<script>
  import { skill } from "./stores.js";

  let navLinks = [
    {
      title: "code",
      imgSrc: "./images/pattern28.jpg"
    },
    {
      title: "music",
      imgSrc: "./images/pattern49.jpg"
    },
    {
      title: "words",
      imgSrc: "./images/pattern47.jpg"
    }
  ];

  function setSkill(skillChosen) {
    skill.set(skillChosen);
  }
</script>

<style>
  section {
    display: flex;
    height: 3em;
    justify-content: space-between;
    margin-bottom: 5em;
  }

  .link {
    border-radius: 10px;
    border: 3px dotted transparent;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
    position: relative;
    height: 4em;
    overflow: hidden;
    width: 100%;
    padding-bottom: 1em;
  }

  .link:hover {
    cursor: pointer;
  }

  #code-link {
    margin-right: 0.5em;
  }

  #words-link {
    margin-left: 0.5em;
  }

  .link--active {
    border: 3px dotted black;
  }

  img {
    position: absolute;
    max-width: 100%;
    width: 100%;
    height: auto;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: -1;
  }

  h2 {
    background: white;
    border-radius: 0px 0px 15px 0px;
    margin: 0;
    padding: 0.25em 0.5em 0.25em 0.25em;
    position: absolute;
  }
</style>

<section>
  {#each navLinks as navLink}
    <div
      class={$skill === navLink.title ? 'link link--active' : 'link'}
      id={`${navLink.title}-link`}
      on:click={() => setSkill(navLink.title)}>
      <h2>{navLink.title.toUpperCase()}</h2>
      <img src={navLink.imgSrc} alt="background" />
    </div>
  {/each}
</section>
