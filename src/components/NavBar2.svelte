<script lang="ts">
  import type { ISection } from '../interfaces/ISection'

  export let sections: ISection[]

  const goToSection = (i: number) => {
    window.scrollTo(0, 931 + 300 * i)
  }
</script>

<style lang="scss">
  $color: rgb(225, 207, 255);

  .nav-bar {
    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 99;

    gap: 15px;
    left: 0;
    right: 0;
    top: 25px;
    margin: auto;

    .boton {
      font-family: 'Poppins', sans-serif;
      height: 50px;
      width: 50px;
      //max-width: fit-content;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 25px;
      border: 1px solid white;
      background-color: inherit;
      transition: 0.5s ease;
      overflow: hidden;
      white-space: nowrap;
      cursor: pointer;

      span {
        display: none;
        margin: 10px;
        font-weight: bold;
      }

      img {
        height: 25px;
        width: 25px;
        margin: 5px;
        filter: invert(1);
      }

      &:hover {
        width: 100px;
        background-color: $color;
        border: $color;
        transition: 0.5s ease;

        img {
          display: none;
        }

        span {
          display: block;
        }
      }
    }
  }
</style>

<div class="nav-bar" contenteditable>
  {#each sections as section, index}
    <button class="boton" on:click={() => goToSection(index)}>
      <img src="./../public/{section.icon}.svg" alt="" />
      <span>{section.title}</span>
    </button>
  {/each}
  <a href="#contacto">
    <button class="boton">
      <img src="./../public/Carta.svg" alt="" />
      <span>Contacto</span>
    </button>
  </a>
</div>
