<script lang="ts">
  import gsap from "gsap";
  let buttonState = "closed";
  import { onMount } from "svelte";
  function transition() {
    if (buttonState === "closed") {
      buttonState = "open";
      gsap.to(".slider ", {
        duration: 0.5,
        top: "0%",
        ease: "power4.out",
      });
    } else {
      buttonState = "closed";
      gsap.to(".slider ", {
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
    <div class="slider">
      <div>
        <p>menu</p>
      </div>
      <div>
        <p>close</p>
      </div>
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
    color: black;
    border-radius: 999px;
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    position: relative;
    width: fit-content;
    height: 3rem;

    .slider {
      position: absolute;
      padding: 0.5em 1.5em;
      display: flex;
      flex-direction: column;
      top: 0;
      left: 0;

      div {
        width: 100%;
        height: 100%;
        padding: 0.5em 1.5em;
        background-color: rgb(211, 244, 26);
        align-items: center;
        justify-content: center;
      }

      div:nth-of-type(2) {
        background-color: black;
        color: rgb(211, 244, 26);
        position: absolute;
        top: 100%;
      }
    }
  }
</style>
