<script lang="ts">
  import PerspectiveText2 from "../PerspectiveText2.svelte";
</script>

<div class="screen">
  <h1>page content goes here</h1>
  <div class="fakeButton">
    <PerspectiveText2 text="menu" />
  </div>
</div>

<style lang="scss">
  .screen {
    background-color: rgb(51, 48, 48);
    width: 100vw;
    min-height: 100vh;
  }

  h1 {
    color: white;
  }

  .fakeButton {
    border-radius: 2rem;
    margin: 2rem;
    width: 5rem;
    height: 2rem;
    background-color: greenyellow;
    color: black;
  }
</style>
