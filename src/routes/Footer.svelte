<script lang="ts">
    import { gsap }  from 'gsap/dist/gsap';
    import {ScrollTrigger} from 'gsap/dist/ScrollTrigger';
    gsap.registerPlugin(ScrollTrigger);
    gsap.to(".footer-underneath", {
      scrollTrigger: {
        trigger: ".newsletter-section",
        start: "top top",
        end: "top 25%",
        scrub: true,
      },
      bottom: -1000,
      duration: 0.5,
    });
</script>

<div class="component">
  <section class="newsletter-section">
    <div class="newsletter-copy">
      <p>
        Get the latest ideas, inspiring trends, innovation and technologies.
      </p>
      <p class="much-more">We have much more than a newsletter.</p>
    </div>
    <div class="newsletter-signup">
      <input
        type="text"
        placeholder="Your email address"
      />
      <span class="subscribe-wrapper">
        <figure>
          <svg
            width="105"
            height="20"
            viewBox="0 0 105 62"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M0 31H103M103 31L73.5 1.5M103 31L73.5 60.5"
              stroke="#010202"
              stroke-width="0.7"
              vector-effect="non-scaling-stroke"
            />
          </svg>
        </figure>
        <button>Subscribe</button>
      </span>
    </div>
  </section>
  <footer class="footer-underneath">
    <div class="big-word">
      <span>F</span>
      <span>F</span>
      <span>A</span>
      <span>U</span>
      <span>N</span>
    </div>
    <div class="footer-info">
      <p>801-4446 St. Laurent Boulevard, Montreal, Quebec</p>
      <p>
        inspired by <a href="https://agencecartier.com/fr/"
          >info@agencecartier.ca</a
        >
      </p>
    </div>
  </footer>
</div>

<style lang="scss">
  .component {
    width: 100%;
    position: relative;
  }
  .newsletter-section {
    background-color: #d0ff71;
    padding: 10rem 2rem 5rem 2rem;
    display: flex;
    justify-content: space-between;
    width: 100%;

    .newsletter-copy {
      p {
        font-size: 1.25rem;
        max-width: 30ch;
        line-height: 1.5;
      }
      .much-more {
        font-size: 3rem;
        max-width: 20ch;
        font-weight: 600;
        margin-top: 1rem;
        line-height: 0.9;
      }
    }

    .subscribe-wrapper {
      display: flex;
      overflow: hidden;
      button {
        background-color: transparent;
        border: none;
        position: relative;
        width: fit-content;
        transform: translateX(-1em);
        padding: 0;
        cursor: pointer;

        &::after {
          content: "";
          position: absolute;
          top: 80%;
          left: 0;
          width: 100%;
          height: 1px;
          background-color: black;
          transform: scaleX(0);
          transform-origin: left;
        }
      }

      &:hover {
        button {
          transform: translateX(0.5em);
          transition: transform 0.3s cubic-bezier(0.58, 0, 0.85, 0.75);
          &::after {
            transform: scaleX(100%);
            transition: transform 0.3s cubic-bezier(0.58, 0, 0.85, 0.75);
          }
        }

        figure {
          transform: translateX(0em);
          transition: transform 0.3s cubic-bezier(0.58, 0, 0.85, 0.75);
        }
      }

      figure {
        margin: 0;
        transform: translateX(-1em);
        svg {
          width: 1em;
        }
      }
    }

    .newsletter-signup {
      display: flex;
      flex-direction: column;
      gap: 0.5rem;

      input {
        background-color: transparent;
        border: none;
        border-bottom: 1px solid black;
        padding: 1rem 1rem 0 1rem;
        &:focus {
          outline: none;
        }
        &::placeholder {
          font-size: 1.25rem;
        }
      }
    }
  }

  .footer-underneath {
    background-color: #000;
    width: 100%;
    color: #fff;
    padding: 1.5rem;
    display: flex;
    flex-direction: column;
    position: absolute;
    bottom: -100px;
    z-index: -1;

    .footer-info {
      padding-left: calc(100vw / 48);
      p {
        margin-bottom: 1rem;
      }
      a {
        color: white;
        text-decoration: underline;
        cursor: pointer;
      }
    }

    .big-word {
      display: flex;
      gap: 0.125rem;
      margin-bottom: 5rem;
      justify-content: space-between;

      span {
        font-size: calc(100vw / 4);
        line-height: 0.9;
        font-weight: 700;
      }
    }
  }
</style>
