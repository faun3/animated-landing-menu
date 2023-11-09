<script>
  import "../global.css";
  import Header from "./Header.svelte";
  import PinnedFooter from "./PinnedFooter.svelte";
</script>

<div>
  <Header />
  <main>
    <slot />
  </main>
  <PinnedFooter />
</div>
