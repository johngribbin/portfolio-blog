<script>
  let projects = [
    {
      title: "Building Pictures",
      releases: [
        {
          year: 2011,
          title: "Training Up My Soul (EP)",
          url: "https://open.spotify.com/embed/album/0vOe4kvOTP9vjNl9mRW7tj"
        },
        {
          year: 2013,
          title: "West Orchard (album)",
          url: "https://open.spotify.com/embed/album/39EKHOTWE3qSYZkAhv4K0D"
        },
        {
          year: 2018,
          title: "If Only for a Day (single)",
          url: "https://open.spotify.com/embed/album/2A68jiqrgqkMSFuzh700a8"
        }
      ],
      playlist: "https://open.spotify.com/embed/album/39EKHOTWE3qSYZkAhv4K0D"
    },
    {
      title: "Tamper",
      releases: [
        {
          year: 2015,
          title: "Tamper (EP)",
          url: "https://open.spotify.com/embed/album/04GctAOVjACcWuTKzOBjpt"
        },
        {
          year: 2016,
          title: "Bought and Sold (EP)",
          url: "https://open.spotify.com/embed/album/6clNFyBH1taw3nFJHQXdYT"
        },
        {
          year: 2017,
          title: "Eagle Bridge (EP)",
          url: "https://open.spotify.com/embed/album/2uxh36EwPTf0UBdmzeyz88"
        }
      ],
      playlist: "https://open.spotify.com/embed/album/2uxh36EwPTf0UBdmzeyz88"
    }
  ];

  let playlist = "https://open.spotify.com/embed/album/2uxh36EwPTf0UBdmzeyz88";

  function changePlaylist(projectTitle, releaseUrl) {
    projects = projects.map(project => {
      if (project.title !== projectTitle) {
        return project;
      }

      if (project.title === projectTitle) {
        return { ...project, playlist: releaseUrl };
      }
    });
  }
</script>

<style>
  .copy {
    margin-bottom: 3em;
    line-height: 1.2;
  }

  .copy p {
    margin-bottom: 1em;
    font-size: 25px;
  }

  .projects__wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    margin: 3em 0em 2em 0em;
  }

  .project {
    border: 1px solid grey;
    padding: 1em;
    width: 300px;
  }

  .project h2 {
    margin-bottom: 1em;
  }

  ul {
    padding-left: 1em;
  }

  li {
    list-style-type: square;
    margin-bottom: 1em;
  }

  .project p {
    color: rgb(0, 100, 200);
    text-decoration: none;
  }

  .project p:hover {
    cursor: pointer;
    text-decoration: underline;
  }

  .project p:visited {
    color: rgb(0, 80, 160);
  }
</style>

<section>
  <div class="copy">
    <p>
      I started releasing music in 2011 under the pseudonym Building Pictures.
      This project helped me to move from Northern Ireland to the United States.
      In more recent years I have been releasing music with my friend Aaron for
      our band Tamper.
    </p>
  </div>

  <div class="projects__wrapper">
    {#each projects as project (project.title)}
      <div class="project">
        <h2>{project.title}</h2>
        <ul>
          {#each project.releases as release (release.year)}
            <li>
              <p on:click={changePlaylist(project.title, release.url)}>
                {release.year} - {release.title}
              </p>
            </li>
          {/each}
        </ul>
        <iframe
          title="spotify playlist"
          src={project.playlist}
          width="300"
          height="80"
          frameborder="0"
          allowtransparency="true"
          allow="encrypted-media" />
      </div>
    {/each}
  </div>

</section>
