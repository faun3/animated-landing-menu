<script lang="ts">
  import gsap from "gsap";
  let buttonState = "closed";
  import { onMount } from "svelte";
  function transition() {
    if (buttonState === "closed") {
      buttonState = "open";
      gsap.to(".expanding-menu div:nth-of-type(2)", {
        duration: 0.5,
        top: "0%",
        ease: "power4.out",
      });
    } else {
      buttonState = "closed";
      gsap.to(".expanding-menu div:nth-of-type(2)", {
        duration: 0.5,
        top: "100%",
        ease: "power4.out",
      });
    }
  }
</script>

<nav class="navbar">
  <span class="">faun</span>
  <button
    class={`expanding-menu ${buttonState}`}
    on:click={transition}
  >
    <div>
      <p>menu</p>
    </div>
    <div>
      <p>close</p>
    </div>
  </button>
</nav>

<style lang="scss">
  .navbar {
    font-family: "Space Grotesk", sans-serif;
    display: flex;
    justify-content: space-between;
    padding: 1rem 2rem;
    align-items: center;
    min-height: 2rem;
    background-color: rgb(107, 103, 103);
    color: white;
  }

  .expanding-menu {
    border: none;
    background-color: rgb(211, 244, 26);
    color: black;
    border-radius: 999px;
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    position: relative;
    overflow: hidden;

    div {
      width: 100%;
      height: 100%;
      padding: 0.5em 1.5em;
    }

    div:nth-of-type(2) {
      background-color: black;
      color: rgb(211, 244, 26);
      position: absolute;
      top: 100%;
    }
  }
</style>
