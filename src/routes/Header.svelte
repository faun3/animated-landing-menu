<script>
  import gsap from "gsap";
</script>

<nav class="navbar">
  <span class="">faun</span>
  <button class="expanding-menu">menu</button>
</nav>

<style lang="scss">
  .navbar {
    font-family: "Space Grotesk", sans-serif;
    display: flex;
    justify-content: space-between;
    padding: 1rem 2rem;
    align-items: center;
    min-height: 2rem;
    background-color: black;
    color: white;
  }

  .expanding-menu {
    border: none;
    background-color: rgb(157, 244, 26);
    color: black;
    border-radius: 999px;
    padding: 0.5em 1em;
    text-transform: uppercase;
  }
</style>
