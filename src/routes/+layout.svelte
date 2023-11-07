<script>
  import "../global.css";
  import Header from "./Header.svelte";
</script>

<div>
  <Header />
  <main>
    <slot />
  </main>
</div>
