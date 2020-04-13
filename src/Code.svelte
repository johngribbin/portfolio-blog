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
  .blurb {
    margin-bottom: 1em;
    line-height: 1.2em;
  }

  .projects__wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    margin: 1em 0em 2em 0em;
  }

  .project {
    border: 1px solid grey;
    padding: 1em;
    margin-top: 2em;
    width: 300px;
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

  <h2 class="blurb">
    Currently I am employed by Consensys where I lead all front-end development
    (mobile and web) on space sustainability project
    <a href="https://trusat.org" target="_blank" rel="noopener noreferrer">
      TruSat.
    </a>
    Some of my recent work:
  </h2>

  <div class="projects__wrapper">
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
