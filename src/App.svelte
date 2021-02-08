<script>
  import page from "page";
  import Uses from "./pages/Uses.svelte";
  import Writing from "./pages/Writing.svelte";
  import Home from "./pages/Home.svelte";
  import NotFound from "./pages/NotFound.svelte";

  import Nav from "./components/Nav.svelte";

  let current = Home;
  let postId;
  
  let params;
  $: console.log(params);

  page("/", () => (current = Home));
  page("/uses", () => (current = Uses));
  page("/writing", () => (current = Writing));
  page("/writing/:postid", (ctx) => {
    console.log("something");
    console.log(ctx.params.postid)
  });
  page("*", () => (current = NotFound));
  page.start();
</script>

<div
  id="app-wrapper"
  class="h-screen w-full bg-gray-800 text-white flex justify-center"
>
  <div
    id="inner-wrapper"
    class="h-full flex items-center flex-col py-10 max-w-4xl flex-1 mx-12"
  >
    <Nav />
    <svelte:component this={current} {...params} />
  </div>
</div>
