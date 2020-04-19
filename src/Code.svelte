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
  .skills {
    border: 1px solid red;
    margin-bottom: 4em;
    max-width: 900px;
  }

  p {
    margin-bottom: 1em;
  }

  .skills ul {
    display: flex;
    list-style-type: circle;
    flex-wrap: wrap;
    margin-top: 0.5em;
  }

  .skills li {
    margin: 0.5em 2em 0em 1.25em;
  }

  .projects__wrapper {
    border: 1px solid red;
    max-width: 900px;
  }

  .projects__wrapper h2 {
    margin-bottom: 1em;
  }

  .project {
    display: flex;
    margin-bottom: 6em;
    width: 900px;
  }

  .project img {
    height: auto;
    max-width: 600px;
    width: 100%;
  }

  .project h2 {
    margin-bottom: 0.25em;
  }

  .project p {
    margin-bottom: 1em;
  }

  .project__content-wrapper {
    margin-left: 1em;
    width: 300px;
  }

  .project__content-wrapper h3 {
    font-weight: bold;
  }

  .project__content-wrapper ul {
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
</style>

<section>
  <div class="skills">
    <h1>Skills</h1>
    <ul>
      <li>JavaScript ES6</li>
      <li>React</li>
      <li>React Native</li>
      <li>Git</li>
      <li>HTML & CSS</li>
      <li>Formik</li>
      <li>Sass</li>
      <li>Styled-Components</li>
      <li>Svelte</li>
      <li>Redux</li>
      <li>AWS</li>
      <li>Netlify</li>
      <li>Firebase</li>
      <li>Agile Software Development</li>
      <li>Test-driven Development</li>
      <li>Node</li>
      <li>Solidity</li>
      <li>Python</li>
    </ul>
  </div>

  <div class="projects__wrapper">
    {#each projects as project}
      <div class="project">
        <img src={project.imgSrc} alt={project.title} />
        <div class="project__content-wrapper">
          <h2>{project.title}</h2>
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
