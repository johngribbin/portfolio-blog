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

  .blurb {
    line-height: 1.2em;
    margin-bottom: 1em;
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
  <h2 class="blurb">Sometimes I enjoy writing.</h2>

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
