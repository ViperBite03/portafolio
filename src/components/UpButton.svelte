<script lang="ts">
  import { onMount } from 'svelte'

  let HTMLGoToStart
  let visible: boolean = false

  onMount(() => {
    const HTMLPages: HTMLElement = document.querySelector('.paginado')
    const topDistance: number = window.scrollY + HTMLPages.getBoundingClientRect().top

    document.addEventListener('scroll', () => (visible = window.scrollY >= topDistance))
  })

  let goToStart = () => window.scrollTo(0, 0)
</script>

<style lang="scss">
  $color: rgb(225, 207, 255);

  .upButton {
    position: fixed;
    background-color: inherit;
    border: 1px solid white;
    height: 75px;
    width: 75px;
    border-radius: 75px;
    z-index: 99;
    cursor: pointer;

    bottom: 25px;
    right: 25px;

    backdrop-filter: blur(3px);
    transition: 0.2s ease;

    display: none;
    justify-content: center;
    align-items: center;

    &.visible {
      display: flex;
    }

    &:hover {
      background-color: $color;
      border: $color;
      transition: 0.2s ease;
    }

    svg {
      transform: rotate(90deg);
    }
  }
</style>

<button class="upButton" class:visible on:click={goToStart} bind:this={HTMLGoToStart}>
  <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512">
    <path fill="none" stroke="#FFFFFF" stroke-linecap="round" stroke-linejoin="round" stroke-width="45" d="M328 112L184 256l144 144">
    </path>
  </svg>
</button>
