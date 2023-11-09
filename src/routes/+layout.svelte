<script>
  import "../global.css";
  import Header from "./Header.svelte";
  import PinnedFooter from "./PinnedFooter.svelte";
</script>

<div class="my-website-lol">
  <Header />
  <main>
    <slot />
  </main>
  <PinnedFooter />
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
