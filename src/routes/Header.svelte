<script lang="ts">
  import gsap from "gsap";
  import PerspectiveText from "./PerspectiveText.svelte";

  let buttonState = "closed";
  import { onMount } from "svelte";
  function transition() {
    if (buttonState === "closed") {
      buttonState = "open";
      gsap.to(".slider ", {
        duration: 0.5,
        top: "-100%",
        ease: "power4.out",
      });
    } else {
      buttonState = "closed";
      gsap.to(".slider ", {
        duration: 0.5,
        top: "0%",
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
      <div class="element">
        <div class="perspectiveText">
          <p>menu</p>
          <p>menu</p>
        </div>
      </div>
      <div class="element">
        <div class="perspectiveText">
          <p>close</p>
          <p>close</p>
        </div>
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
    width: 100%;
  }

  .expanding-menu {
    border: none;
    height: 3rem;
    width: 5rem;
    overflow: hidden;
    border-radius: 2rem;
    cursor: pointer;
    padding: 0;

    .slider {
      position: relative;
      width: 100%;
      height: 100%;

      .element {
        width: 100%;
        height: 100%;
        background-color: rgb(211, 244, 26);

        &:nth-of-type(2) {
          background-color: black;
          p {
            color: rgb(211, 244, 26);
          }
        }
        &:hover {
          .perspectiveText {
            p {
              transition: all 0.75s cubic-bezier(0.075, 0.82, 0.165, 1);
              transform-style: preserve-3d;
              &:nth-of-type(2) {
                transform: rotateX(0deg) translateY(calc(-100% - 0.9rem));
                transform-origin: top center;
                opacity: 1;
              }
              &:nth-of-type(1) {
                transform: rotateX(90deg);
                opacity: 0;
              }
            }
          }
        }
      }
    }
    .perspectiveText {
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      text-transform: uppercase;
      overflow: hidden;
      position: relative;
      transform-style: preserve-3d;

      p {
        transition: all 1.95s cubic-bezier(0.075, 0.82, 0.165, 1);
        &:nth-of-type(2) {
          position: absolute;
          top: 100%;
          transform: rotateX(-90deg);
          transform-origin: top center;
          pointer-events: none;
          opacity: 0;
        }
        &:nth-of-type(1) {
          transform-origin: top center;
          pointer-events: none;
        }
      }
    }
  }
</style>
