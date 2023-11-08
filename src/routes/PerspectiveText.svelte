<script lang="ts">
  export let text: string;
</script>

<div class="perspectiveText">
  <p>{text}</p>
  <p>{text}</p>
</div>

<style lang="scss">
  .perspectiveText {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    text-transform: uppercase;
    overflow: hidden;

    p {
      padding: 1rem;
      &:nth-of-type(2) {
        position: absolute;
        transform: rotateX(-90deg);
        transform-origin: top;
      }
    }
  }
</style>
