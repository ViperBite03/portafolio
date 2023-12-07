<script lang="ts">
  import type { ISection } from '../interfaces/ISection'
  export let sections: ISection[]
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

    .btn {
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
      backdrop-filter: blur(3px);

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

<div class="nav-bar">
  {#each sections as section, index}
    <button class="btn go-to-sections" meta-index={index}>
      <img src="{section.icon}.svg" alt="" />
      <span>{section.title}</span>
    </button>
  {/each}
  <a href="#contacto">
    <button class="btn">
      <img src="Carta.svg" alt="" />
      <span>Contacto</span>
    </button>
  </a>
</div>
