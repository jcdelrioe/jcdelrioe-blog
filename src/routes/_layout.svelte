<script>
  import Nav from "../components/Nav.svelte";
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";
  import Main from "../components/Main.svelte";

  export let segment;
</script>

<Header />
<Nav {segment} />

<Main>
  <slot />
</Main>

<Footer />
