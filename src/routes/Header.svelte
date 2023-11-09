<script lang="ts">
  import gsap from "gsap";

  let buttonState = "closed";
  function transition() {
    if (buttonState === "closed") {
      buttonState = "open";
      // animate the menu OPENING
      const tl = gsap.timeline();
      tl.to(".slider ", {
        duration: 0.4,
        top: "-100%",
        ease: "power4.out",
      });
      tl.to(
        ".menu-box",
        {
          duration: 0.5,
          width: "40rem",
          height: "30rem",
          translateX: "1rem",
          translateY: "-1rem",
        },
        ">-0.4"
      );
      tl.to(".menu-content", {
        opacity: 1,
        duration: 0.3,
      });

      // gsap.to(".slider ", {
      //   duration: 0.5,
      //   top: "-100%",
      //   ease: "power4.out",
      // });
      // gsap.to(".menu-box", {
      //   duration: 0.5,
      //   width: "40rem",
      //   height: "30rem",
      //   translateX: "1rem",
      //   translateY: "-1rem",
      // });
      // gsap.to(".menu-content", {
      //   opacity: 1,
      //   duration: 0.3,
      // });
    } else {
      buttonState = "closed";
      const tl = gsap.timeline();
      tl.to(".slider ", {
        duration: 0.4,
        top: "0%",
        ease: "power4.out",
      });
      tl.to(
        ".menu-content",
        {
          opacity: 0,
          duration: 0.3,
        },
        ">-0.2"
      );
      tl.to(
        ".menu-box",
        {
          duration: 0.5,
          width: "5rem",
          height: "3rem",
          translateX: "0rem",
          translateY: "0rem",
        },
        ">-0.1"
      );
    }
  }
</script>

<nav class="navbar">
  <span class="">faun</span>
  <div class="relative-wrapper">
    <div class="menu-wrapper">
      <div class={`menu-box ${buttonState}`}>
        <div class="menu-content">
          <div class="content-ctas">
            <span class="cta-with-arrow">
              <figure>
                <svg
                  width="105"
                  height="62"
                  viewBox="0 0 105 62"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M0 31H103M103 31L73.5 1.5M103 31L73.5 60.5"
                    stroke="#010202"
                    stroke-width="2"
                    vector-effect="non-scaling-stroke"
                  />
                </svg>
              </figure>
              <p>Projects</p>
            </span>
            <span class="cta-with-arrow">
              <figure>
                <svg
                  width="105"
                  height="62"
                  viewBox="0 0 105 62"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M0 31H103M103 31L73.5 1.5M103 31L73.5 60.5"
                    stroke="#010202"
                    stroke-width="2"
                    vector-effect="non-scaling-stroke"
                  />
                </svg>
              </figure>
              <p>Agency</p>
            </span>
            <span class="cta-with-arrow">
              <figure>
                <svg
                  width="105"
                  height="62"
                  viewBox="0 0 105 62"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M0 31H103M103 31L73.5 1.5M103 31L73.5 60.5"
                    stroke="#010202"
                    stroke-width="2"
                    vector-effect="non-scaling-stroke"
                  />
                </svg>
              </figure>
              <p>Expertise</p>
            </span><span class="cta-with-arrow">
              <figure>
                <svg
                  width="105"
                  height="62"
                  viewBox="0 0 105 62"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M0 31H103M103 31L73.5 1.5M103 31L73.5 60.5"
                    stroke="#010202"
                    stroke-width="2"
                    vector-effect="non-scaling-stroke"
                  />
                </svg>
              </figure>
              <p>Careers</p>
            </span><span class="cta-with-arrow">
              <figure>
                <svg
                  width="105"
                  height="62"
                  viewBox="0 0 105 62"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M0 31H103M103 31L73.5 1.5M103 31L73.5 60.5"
                    stroke="#010202"
                    stroke-width="2"
                    vector-effect="non-scaling-stroke"
                  />
                </svg>
              </figure>
              <p>Contact</p>
            </span>
            <div class="links">
              <div class="links-left">
                <p>Facebook</p>
                <p>Instagram</p>
              </div>
              <div class="links-right">
                <p>LinkedIn</p>
                <p>English</p>
              </div>
            </div>
          </div>
        </div>
      </div>
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
    </div>
  </div>
</nav>

<style lang="scss">
  .navbar {
    font-family: "Nunito Sans", sans-serif;
    display: flex;
    justify-content: space-between;
    padding: 2rem 2rem;
    align-items: center;
    height: 7rem;
    background-color: transparent;
    color: black;
    width: 100%;
    position: fixed;
    top: 0;
    z-index: 1;
  }

  .relative-wrapper {
    position: absolute;
    right: 2rem;
    top: 2rem;
  }

  .menu-wrapper {
    position: relative;
  }

  .menu-box {
    height: 3rem;
    width: 5rem;
    background-color: #d0ff71;
    border-radius: 2rem;
    position: relative;
    overflow: hidden;
    z-index: 2;

    .menu-content {
      position: absolute;
      color: black;
      bottom: 0;
      font-size: 2.5rem;
      display: flex;
      flex-direction: column;
      padding: 0 0 1rem 2rem;
      z-index: 3;

      .content-ctas {
        p {
          margin-bottom: 0.5rem;
          font-weight: 500;
        }

        .cta-with-arrow {
          overflow: hidden;

          display: flex;
          align-items: center;
          gap: 0.5rem;
          p {
            transition: transform 0.6s cubic-bezier(0.075, 0.82, 0.165, 1);
            transform: translateX(-2.5rem);
            margin: 0;
          }
          figure {
            display: inline;
            transform: translateX(-2.5rem);
            transition: transform 0.6s cubic-bezier(0.075, 0.82, 0.165, 1);
            margin: 0;
            svg {
              width: 2rem;
            }
          }

          &:hover {
            figure {
              transform: translateX(0rem);
              transition: transform 0.6s cubic-bezier(0.075, 0.82, 0.165, 1);
            }
            p {
              transform: translateX(0rem);
              transition: transform 0.6s cubic-bezier(0.075, 0.82, 0.165, 1);
            }
          }
        }
      }
    }

    .links {
      display: flex;
      font-size: 1.2rem;
      gap: 1rem;
      margin-top: 1rem;
      width: fit-content;

      .links-left,
      .links-right {
        width: fit-content;
        p {
          position: relative;
          &::after {
            content: "";
            display: block;
            position: absolute;
            width: 100%;
            height: 2px;
            background-color: black;
            transition: transform 0.3s cubic-bezier(0.58, 0, 0.85, 0.75);
            transform: scale(0);
            transform-origin: top left;
          }
          &:hover::after {
            transform: scale(1);
          }
        }
      }
    }
  }

  .expanding-menu {
    border: none;
    height: 3rem;
    width: 5rem;
    overflow: hidden;
    border-radius: 2rem;
    cursor: pointer;
    padding: 0;
    position: absolute;
    top: 0;
    right: 0;
    z-index: 12;

    .slider {
      position: relative;
      width: 100%;
      height: 100%;

      .element {
        width: 100%;
        height: 100%;
        background-color: #d0ff71;

        &:nth-of-type(2) {
          background-color: black;
          p {
            color: #d0ff71;
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
