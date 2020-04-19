<script>
  const projects = [
    {
      title: "TruSat",
      imgSrc: "./images/trusat.jpg",
      description:
        "A citizen-powered, open source system for creating a globally-accessible, trusted record of satellite orbital positions.",
      stack: ["React", "Sass", "Ethers.js", "AWS"],
      code_link: "https://github.com/TruSat/trusat-frontend",
      live_link: "https://trusat.org/"
    },
    {
      title: "Tractor Beam",
      imgSrc: "./images/tractorbeam.jpg",
      description:
        "Mobile application to demonstrate a novel Ethereum onboarding experience using counter-factually deployed smart contracts",
      stack: ["React Native", "Redux", "Formik", "Ethers.js", "Expo"],
      code_link: "https://github.com/johngribbin/tractor-beam",
      live_link: null
    },
    {
      title: "SSA Toshi",
      imgSrc: "./images/ssatoshi.jpg",
      description:
        "A Ethereum smart-contract research project to examine permissioning.",
      stack: ["React", "Solidity", "Truffle", "ethers.js"],
      code_link: "https://github.com/johngribbin/ssa-toshi",
      live_link: "https://ssatoshi.surge.sh/"
    },
    {
      title: "Crypto Hitters",
      imgSrc: "./images/cryptohitters.jpg",
      description:
        "A web app that brings together price changes in crypto assets and the news/gossip that may have caused them.",
      stack: ["React", "Chart.js", "Netlify"],
      code_link: "https://github.com/johngribbin/crypto-hitters",
      live_link: "https://cryptohitters.com"
    }
  ];
</script>

<style>
  .projects__wrapper {
    max-width: 1000px;
  }

  .project {
    display: flex;
    flex-wrap: wrap;
    margin-bottom: 5em;
  }

  .project__image-container {
    margin: 0em 3em 1em 0em;
    max-width: 600px;
  }

  .project__image-container img {
    box-shadow: 10px 15px 25px 0 rgba(0, 0, 0, 0.4);
    width: 100%;
  }

  .project p {
    margin-bottom: 2em;
  }

  .project__content-wrapper {
    width: 300px;
  }

  .project__content-wrapper h3 {
    font-weight: bold;
  }

  .project__content-wrapper p {
    margin-top: 1em;
  }

  .project__content-wrapper ul {
    color: black;
    display: flex;
    flex-wrap: wrap;
    list-style-type: circle;
    margin-left: -0.3em;
  }

  .project__content-wrapper li {
    margin-left: 1.5em;
    margin-top: 0.5em;
  }

  .project__links-wrapper {
    display: flex;
    margin-top: 2em;
  }

  .project__link-button {
    align-items: center;
    border-radius: 5px;
    color: black;
    border: 2px solid black;
    display: flex;
    font-weight: bold;
    margin-right: 1em;
    padding: 0.75em;
  }

  .project__link-button img {
    margin-right: 0.5em;
    width: 32px;
  }

  @media (max-width: 800px) {
    .project__image-container {
      margin: 0em 0em 1em 0em;
    }

    .project__content-wrapper {
      padding: 0em 2em 0em 2em;
    }
  }
</style>

<section>
  <div class="projects__wrapper">
    {#each projects as project}
      <div class="project">
        <div class="project__image-container photo">
          <img src={project.imgSrc} alt={project.title} />
          <div class="glow-wrap">
            <i class="glow" />
          </div>
        </div>

        <div class="project__content-wrapper">
          <h1>{project.title}</h1>
          <p>{project.description}</p>
          <h3>Stack:</h3>
          <ul>
            {#each project.stack as item}
              <li>{item}</li>
            {/each}
          </ul>
          <div class="project__links-wrapper">
            <a
              class="project__link-button"
              href={project.live_link}
              target="_blank"
              rel="noopener noreferrer">
              VIEW APP
            </a>
            <a
              class="project__link-button"
              href={project.code_link}
              target="_blank"
              rel="noopener noreferrer">
              <img src="./images/github-icon.png" alt="github" />
              CODE
            </a>
          </div>
        </div>
      </div>
    {/each}
  </div>

</section>
