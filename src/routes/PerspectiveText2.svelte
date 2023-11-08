<script lang="ts">
  export let text: string;
</script>

<div class="perspText">
  <p>{text}</p>
  <p>{text}</p>
</div>

<style lang="scss">
  .perspText {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    text-transform: uppercase;
    overflow: hidden;
    position: relative;
    transform-style: preserve-3d;

    &:hover {
      p {
        transition: all 0.75s cubic-bezier(0.075, 0.82, 0.165, 1);
        transform-style: preserve-3d;
        &:nth-of-type(2) {
          transform: rotateX(0deg) translateY(calc(-100% - 0.35rem));
          transform-origin: top center;
          opacity: 1;
        }
        &:nth-of-type(1) {
          transform: rotateX(90deg);
          opacity: 0;
        }
      }
    }

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
</style>
