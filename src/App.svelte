<script>
  import { Router } from "@sveltech/routify";
  import { routes } from "@sveltech/routify/tmp/routes";
</script>

<style>
  footer {
    margin: 10em 0em 4em 0em;
    text-align: center;
  }

  a {
    text-decoration: underline;
  }
</style>

<Router {routes} />
<footer>
  <a href="https://github.com/johngribbin/portfolio_2020">
    This website is open-source
  </a>
</footer>
