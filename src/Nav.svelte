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
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    height: 3em;
  }

  div {
    border-radius: 10px;
    border: 3px dotted transparent;
    position: relative;
    width: 100%;
    height: 4em;
    overflow: hidden;
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.028),
      0 6.7px 6.7px rgba(0, 0, 0, 0.042), 0 30px 30px rgba(0, 0, 0, 0.07);
  }

  div:hover {
    border: 3px dotted red;
    cursor: pointer;
    opacity: 0.5;
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
    <div>
      <h2>{navLink.title.toUpperCase()}</h2>
      <img
        src={navLink.imgSrc}
        alt="background"
        on:click={() => setSkill(navLink.title)} />
    </div>
  {/each}
</section>
