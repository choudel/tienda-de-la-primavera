<script lang="ts">
  import Nav from "../lib/nav.svelte";
  import Title from "../lib/title.svelte";
  import Search from "../lib/search.svelte";
  import Card from "../lib/card.svelte";
  import Footer from "../lib/footer.svelte";
  /* @type { import('./$houdini').PageData } */
  export let data;
  $: ({ Item } = data);
</script>

<main>
  <header>
    <Nav />
    {$Item.data.item.item}
  </header>
  <section class="hero">
    <Title />
    <Search />
  </section>
  <section class="container">
    <Card />
    <Card />
    <Card />
    <Card />
  </section>
  <footer>
    <Footer />
  </footer>
</main>

<style lang="scss">
  main {
    display: grid;
    grid-template-rows: 10vmax 35vmax 35vmax 20vmax;
    background: linear-gradient(
        180deg,
        rgba(0, 0, 0, 0) 0%,
        rgba(0, 0, 0, 0.2) 71.35%
      ),
      #a4bc92;
    @media only screen and (max-width: 815px) {
      grid-template-rows: 10vmax auto auto 20vmax;
      padding: 16px;
    }
  }
  header {
    padding: 16px;
  }
  section {
    padding-left: 74px;
    padding-right: 74px;
    @media only screen and (max-width: 815px) {
      padding-left: 16px;
      padding-right: 16px;
    }
  }
  .container {
    display: grid;
    grid-template-columns: auto auto auto auto;
    gap: 8px;
    @media only screen and (max-width: 815px) {
      grid-template-columns: auto;
      grid-template-rows: auto auto auto auto;
    }
  }
  footer {
    padding-left: 16px;
    padding-right: 16px;
    padding-top: 8px;
  }
</style>
