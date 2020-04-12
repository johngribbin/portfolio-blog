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
    console.log(skillChosen);

    skill.set(skillChosen);
  }
</script>

<style>
  section {
    display: flex;
    margin-bottom: 3em;
    justify-content: space-between;
    height: 3em;
  }

  .link__wrapper {
    position: relative;
    width: 100%;
  }

  .link__wrapper:hover,
  .link__wrapper--active:hover {
    cursor: pointer;
    opacity: 1;
  }

  .link__wrapper--active {
    width: 100%;
    border-bottom: 5px solid black;
    padding-bottom: 4.5em;
  }

  #code-link-wrapper {
    margin-right: 0.5em;
  }

  #words-link-wrapper {
    margin-left: 0.5em;
  }

  .link {
    border-radius: 10px;
    border: 3px dotted transparent;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
    position: relative;
    height: 4em;
    overflow: hidden;
    width: 100%;
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
    position: absolute;
    margin: 0;
    padding: 0.25em 0.5em 0.25em 0.25em;
  }
</style>

<section>
  {#each navLinks as navLink}
    <div
      class={navLink.title === $skill ? 'link__wrapper--active' : 'link__wrapper'}
      id={`${navLink.title}-link-wrapper`}>
      <div class="link" on:click={() => setSkill(navLink.title)}>
        <h2>{navLink.title.toUpperCase()}</h2>
        <img src={navLink.imgSrc} alt="background" />
      </div>
    </div>
  {/each}
</section>
