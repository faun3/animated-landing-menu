<script>
  import "../global.css";
  import Header from "./Header.svelte";
  import Footer from "./Footer.svelte";
  export const ssr = false;
</script>

<div class="my-website-lol">
  <Header />
  <main>
    <slot />
  </main>
  <Footer/>
</div>

<style lang="scss">
  .my-website-lol {
    font-family: "Nunito Sans", sans-serif;
    width: 100%;

    main {
      width: 100%;
      overflow-x: hidden;
    }
  }
</style>
