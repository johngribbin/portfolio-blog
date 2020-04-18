<script>
  const posts = [
    {
      title: "An Ethereum Developer’s Guide to User Onboarding",
      link:
        "https://medium.com/crypto-propulsion-laboratory/an-ethereum-developers-guide-to-user-onboarding-97e107d56fe9"
    },
    {
      title: "Some CPL developer thoughts on DevCon IV",
      link:
        "https://medium.com/crypto-propulsion-laboratory/some-cpl-developer-thoughts-on-devcon-iv-f2f2eb68dafa"
    },
    {
      title: "TruSat Knowledge Hub",
      link: "https://learn.trusat.org"
    }
  ];
</script>

<style>
  section {
    display: flex;
    flex-direction: column;
  }

  .copy {
    margin-bottom: 3em;
    line-height: 1.2;
  }

  .copy p {
    margin-bottom: 1em;
    font-size: 25px;
  }

  ul {
    padding-left: 1em;
  }

  li {
    list-style-type: square;
    margin-bottom: 1em;
  }
</style>

<section>
  <div class="copy">
    <p>Sometimes I enjoy writing.</p>
  </div>

  <ul>
    {#each posts as post (post.link)}
      <li>
        <a href={post.link} target="_blank" rel="noopener noreferrer">
          {post.title}
        </a>
      </li>
    {/each}

  </ul>

</section>
