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
      stack: ["React", "Sass", "Ethers.js", "AWS"],
      purpose:
        "This project was created with the goal of providing the world with a community driven and fully transparent alternative to the centralized services that offer orbital prediction data for satellites. The big challenge for us was to combine education on the “sport” of tracking satellites and at the same time ensure that the UX was optimal. We paired the app with docs that are as much about learning how to track a sat as they are about submitting data to the platform.",
      stack_explainer:
        "All state management is handled by React Hooks, without the need for an additional library like Redux. All users are identified by their pseudonymous Ethereum addresses, with authentication aided with the help of Ethers.js and the MetaMask plugin. We also built a custom signup experience that encrypts an Ethereum wallet and emails this to the user as a “secret” to allow users to identify themselves. All assets are stored in AWS S3 buckets.",
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
        "This was an R&D project at ConsenSys to showcase a new way to on-boarding users to the Ethereum network that was made possible by the introduction of the CREATE2 opcode. In a nutshell, decentralized app users can now receive and withdraw tokens from their account without requiring the additional step of acquiring Ether to pay transaction costs. The transaction fees are instead covered by the application, after getting permission to debit the tokens the equivalent amount. The biggest challenge was abstracting as much complexity away from the user as possible while at same time being transparent about the permissions that the user was granting to the app creators under the hood.",
      stack_explainer:
        "I used React-Native to build out the app. As the state for the application grew I decided to introduce Redux to handle the state management.",
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
        "I created this project at ConsenSys Space to help provide an example to my team mates of how smart contract permissions could be used for community curation of satellite observations in TruSat. On page loads a “burner wallet” is generated in the browser to provide the user with a unique Ethereum address (a pseudonymous identity). After adding some test-net Ether to their address, visitors can clicking the “confirm” button under each picture to update the state of a smart contract. This step essentially symbolizes how anyone could add a vote of confidence to a sat observation. Some of the permissions in the contract prevent Ethereum addresses that submit observations from voting on their own submissions.",
      stack_explainer:
        "I used Truffle to deploy the smart contracts to an Ethereum testnet. The front end was built with React, and Ethers.js was used to help interact with the deployed smart contract. ",
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
        "When I first got interested in the cryptocurrency space I would spend a lot of time jumping between websites that offer price data and various reddit forums that gather gossip or news about a given project. Cryptohitters pulls both of these feeds under one page and throws in a bonus of a chart of the last 60 days price action that can be useful for placing a trade.",
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
    display: flex;
    flex-wrap: wrap;
    margin-bottom: 5em;
  }

  .project__image-container {
    margin: 0em 3em 1em 0em;
    width: 550px;
  }

  .project__image-container img {
    box-shadow: 10px 15px 25px 0 rgba(0, 0, 0, 0.3);
    width: 100%;
  }

  .project p {
    margin-bottom: 1em;
  }

  .project__content-wrapper {
    width: 550px;
  }

  .project__content-wrapper p {
    margin-top: 1em;
  }

  .project__content-wrapper ul {
    color: black;
    display: flex;
    flex-wrap: wrap;
    list-style-type: circle;
    margin-bottom: 1em;
    margin-left: 0.7em;
  }

  .project__content-wrapper li {
    font-size: 18px;
    font-weight: bold;
    margin: 0.25em 1.5em 0.25em 0.5em;
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

    .project__content-wrapper h1 {
      margin-top: 0.75em;
    }
  }
</style>

<section>
  {#if visible}
    {#each projects as project}
      <div in:fade={{ duration: 1000 }} class="project">
        <div class="project__image-container photo">
          <img src={project.imgSrc} alt={project.title} />
          <div class="glow-wrap">
            <i class="glow" />
          </div>
        </div>

        <div class="project__content-wrapper">
          <h1>{project.title}</h1>
          <p>{project.description}</p>
          <p>{project.purpose}</p>
          <ul>
            {#each project.stack as item}
              <li>{item}</li>
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
                VIEW APP
              </a>
            {/if}
            <a
              class="project__link-button"
              href={project.code_link}
              target="_blank"
              rel="noopener noreferrer">
              <img
                src="https://live.staticflickr.com/65535/49798531141_f7e30a48c0_t.jpg"
                alt="github" />
              CODE
            </a>
          </div>
        </div>
      </div>
    {/each}
  {/if}
</section>
