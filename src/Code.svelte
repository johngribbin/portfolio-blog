<script>
  import { onMount } from "svelte";
  import { fade } from "svelte/transition";

  const projects = [
    {
      title: "TruSat",
      imgSrc:
        "https://live.staticflickr.com/65535/49797961373_70a4eab969_o.jpg",
      description:
        "A citizen-powered, open source system for creating a globally-accessible, trusted record of satellite orbital positions.",
      stack: ["React", "Sass", "Ethers.js", "AWS", "Docusaurus"],
      purpose:
        "Tracking satellites is a little tricky! The big challenge was to provide an accessible combination of educational tools with solid UX to help on-board those who are unfamiliar with the sport.",
      stack_explainer:
        "All state management is handled by React Hooks, without the need for an additional library like Redux. All users are identified by their pseudonymous Ethereum address, with authentication aided by Ethers.js and the MetaMask plugin. A custom email/password signup experience was created to onboard users via encrypted Ethereum wallets. All assets are stored in AWS S3 buckets. The docs were built with a Docusaurus starter.",
      code_link: "https://github.com/TruSat/trusat-frontend",
      live_link: "https://trusat.org/"
    },
    {
      title: "Tractor Beam",
      imgSrc:
        "https://live.staticflickr.com/65535/49798515956_658f99571c_o.jpg",
      description:
        "Mobile application to demonstrate a novel Ethereum onboarding experience using counter-factually deployed smart contracts",
      stack: ["React Native", "Redux", "Formik", "Ethers.js", "Expo"],
      purpose:
        "This was an R&D project to showcase a new way to on-boarding users to the Ethereum network that was made possible by the introduction of the CREATE2 opcode. In a nutshell, decentralized app users can now receive and withdraw tokens from their account without requiring the additional step of acquiring Ether to pay transaction costs. The biggest challenge was abstracting a bunch of complexity away from the user while at the same time being transparent about the permissions that the user was granting to the app creators under the hood.",
      stack_explainer:
        "React-Native was used to build out the app. As the state for the application, Redux was introduced to handle state management.",
      code_link: "https://github.com/johngribbin/tractor-beam",
      live_link: null
    },
    {
      title: "SSA Toshi",
      imgSrc:
        "https://live.staticflickr.com/65535/49797975653_7bf619754b_o.jpg",
      description:
        "A Ethereum smart-contract research project to examine permissioning.",
      stack: ["React", "Solidity", "Truffle", "ethers.js"],
      purpose:
        "I created this project to provide an example to my team mates of how smart contract permissions could be used for community curation of satellite observations in TruSat. A “burner wallet” with a unique Ethereum address is generated for each visitor to the page (a pseudonymous identity). After procuring some test-net Ether to their address, visitors can click the “confirm” button under each picture to update the state of a smart contract. This process is symbolic of how anyone (permission-less) could add a vote of confidence to a satellite observation. Permissions in the contract include a check to prevent Ethereum addresses that submit observations from voting on their own submissions.",
      stack_explainer:
        "Truffle was used to deploy the smart contract. The front end was built with React, and Ethers.js was used to help users interact with the smart contract.",
      code_link: "https://github.com/johngribbin/ssa-toshi",
      live_link: "https://ssatoshi.surge.sh/"
    },
    {
      title: "Crypto Hitters",
      imgSrc:
        "https://live.staticflickr.com/65535/49798834422_f950cde020_o.jpg",
      description:
        "A web app that brings together price changes in crypto assets and the news/gossip that may have caused them.",
      stack: ["React", "Chart.js", "Netlify"],
      purpose:
        "When I first got interested in the cryptocurrency space I would spend a lot of time jumping between price data sites and reddit forums that gather gossip or news about a given project. Cryptohitters pulls both of these feeds into one place.",
      stack_explainer:
        "The data for the app is provided by the CoinMarketCap, Reddit and CryptoCompare APIs. Chart.js was really useful for putting together a chart to show the previous 60 day’s price action for each asset.",
      code_link: "https://github.com/johngribbin/crypto-hitters",
      live_link: "https://cryptohitters.com"
    }
  ];

  let visible = false;

  onMount(() => {
    visible = true;
  });
</script>

<style>
  .project {
    border: 1px solid rgba(14, 237, 207, 0.2);
    border-radius: 5px;
    box-shadow: 5px 5px 10px 0px rgba(14, 237, 207, 0.3);
    display: flex;
    margin-top: 6em;
    padding: 2em 1em;
  }

  .project__image-container {
    margin-right: 2em;
    width: 50%;
  }

  .project__image-container img {
    display: block;
    height: auto;
    width: 100%;
  }

  .project__content-wrapper {
    width: 50%;
  }

  .project__content-wrapper h2 {
    font-style: italic;
    margin: 0.75em 0;
  }

  .project__content-wrapper ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: circle;
    margin: 1em;
  }

  .project__content-wrapper li {
    margin: 0.25em 1.5em 0.25em 0.5em;
  }

  .project__links-wrapper {
    display: flex;
    margin-top: 2em;
  }

  .project__link-button {
    align-items: center;
    background: black;
    border-radius: 5px;
    border: 2px solid white;
    color: white;
    display: flex;
    font-weight: bold;
    margin-right: 1em;
    padding: 0.75em;
  }

  .project__link-button:hover {
    border-color: rgba(14, 237, 207, 0.8);
    color: rgba(14, 237, 207, 0.8);
  }

  /* Tablet */
  @media (max-width: 1000px) {
    .project {
      flex-wrap: wrap;
    }

    .project__image-container {
      margin-right: 0em;
      width: 100%;
    }

    .project__image-container img {
      width: 100%;
    }

    .project__content-wrapper {
      margin-top: 2em;
      width: 100%;
    }
  }
</style>

<section>
  {#if visible}
    {#each projects as project}
      <div in:fade={{ duration: 1000 }} class="project">
        <div class="project__image-container">
          <img src={project.imgSrc} alt={project.title} />
        </div>

        <div class="project__content-wrapper">
          <h1>{project.title}</h1>
          <h2>{project.description}</h2>
          <p>{project.purpose}</p>
          <ul>
            {#each project.stack as item}
              <li>
                <p>{item}</p>
              </li>
            {/each}
          </ul>
          <p>{project.stack_explainer}</p>
          <div class="project__links-wrapper">
            {#if project.live_link}
              <a
                class="project__link-button"
                href={project.live_link}
                target="_blank"
                rel="noopener noreferrer">
                APP
              </a>
            {/if}
            <a
              class="project__link-button"
              href={project.code_link}
              target="_blank"
              rel="noopener noreferrer">
              CODE
            </a>
          </div>
        </div>
      </div>
    {/each}
  {/if}
</section>
