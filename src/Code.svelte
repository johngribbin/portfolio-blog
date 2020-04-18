<script>
  const projects = [
    {
      title: "TruSat",
      description:
        "A citizen-powered, open source system for creating a globally-accessible, trusted record of satellite orbital positions.",
      code_link: "https://github.com/TruSat/trusat-frontend",
      live_link: "https://trusat.org/"
    },
    {
      title: "Tractor Beam",
      description:
        "Mobile application (React Native) to demonstrate a novel Ethereum onboarding experience using counter-factually deployed smart contracts",
      code_link: "https://github.com/johngribbin/tractor-beam",
      live_link: null
    },
    {
      title: "SSA Toshi",
      description:
        "A smart-contract research project to examine permissioning.",
      code_link: "https://github.com/johngribbin/ssa-toshi",
      live_link: "https://ssatoshi.surge.sh/"
    },
    {
      title: "Crypto Hitters",
      description:
        "A web app that brings together price changes in crypto assets and the news/gossip that may have caused them.",
      code_link: "https://github.com/johngribbin/crypto-hitters",
      live_link: "https://cryptohitters.com"
    }
  ];
</script>

<style>
  .copy {
    //border: 1px solid red;
    margin-bottom: 3em;
    line-height: 1.2em;
  }

  .copy p {
    margin-bottom: 1em;
  }

  .copy ul {
    display: flex;
    list-style-type: circle;
    flex-wrap: wrap;
    margin-top: 0.5em;
  }

  .copy li {
    margin: 0.5em 2em 0em 1.25em;
  }

  .projects__wrapper {
    //border: 1px solid red;
    margin-bottom: 6em;
  }

  .projects__wrapper h2 {
    margin-bottom: 1em;
  }

  .project {
    border: 1px solid grey;
    padding: 1em 0;
    margin-bottom: 2em;
    width: 100%;
  }

  .project h2 {
    margin-bottom: 0.25em;
  }

  .project p {
    margin-bottom: 1em;
  }

  .project__links-wrapper {
    display: flex;
    justify-content: space-between;
  }
</style>

<section>

  <div class="copy">
    <p>
      After reading the Bitcoin whitepaper I decided I should learn to code.
      Currently I lead all front-end development at
      <a
        href="https://consensys.space"
        target="_blank"
        rel="noopener noreferrer">
        ConsenSys Space.
      </a>
      We build awesome open-source collaboration platforms to diversify,
      democratize, and decentralize space endeavors. I spend a lot of time in
      React and Svelte projects, but I am very much framework agnostic.
    </p>
  </div>

  <div class="copy">
    <h2>Skills</h2>
    <ul>
      <li>JavaScript ES6</li>
      <li>React</li>
      <li>React Native</li>
      <li>Git</li>
      <li>HTML & CSS</li>
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
    <h2>Projects</h2>
    {#each projects as project}
      <div class="project">
        <h2>{project.title}</h2>
        <p>{project.description}</p>
        <div class="project__links-wrapper">
          <a href={project.live_link} target="_blank" rel="noopener noreferrer">
            Live
          </a>
          <a href={project.code_link} target="_blank" rel="noopener noreferrer">
            Code
          </a>
        </div>

      </div>
    {/each}
  </div>

</section>
