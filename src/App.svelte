<!-- //============================ Script ================================= -->
<script>
  import router from "page";
  import NavBar from "./components/NavBar.svelte";
  import Footer from "./components/Footer.svelte";
  import routes from "./routes/routes";

  let page;
  let params;

  routes.forEach((route) => {
    router(
      route.path,

      // Set the params variable to the context.
      // We use this on the component initialisation
      (ctx, next) => {
        params = ctx.params;
        next();
      },

      // Check if auth is valid. If so, set the page to the component
      // otherwise redirect to login.
      () => {
        if (route.auth && !user) {
          router.redirect("/login");
        } else {
          page = route.component;
        }
      }
    );
  });

  // Set up the router to start and actively watch for changes
  router.start();
</script>

<!-- //============================ HTML =================================== -->
<header>
  <NavBar />
</header>
<main class="backColor_1 w-100 h-100 mt-12">
  <svelte:component this={page} />
</main>
<Footer />

<!-- //============================ Style ================================== -->
<style lang="postcss" global>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  body {
    background-color: #212529;
  }

  .backColor_1 {
    background-color: #212529;
  }
</style>
