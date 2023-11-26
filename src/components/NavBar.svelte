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
    background-color: $color;
    height: fit-content;
    width: fit-content;
    z-index: 99;

    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 15px;

    border-radius: 100px;
    padding: 10px 15px;
    left: 0;
    right: 0;
    top: 15px;
    margin: auto;

    .boton {
      cursor: pointer;
      padding: 7px 14px;
      border: none;
      border-radius: 20px;

      font-size: 13px;
      font-weight: bold;
      font-family: 'Poppins', sans-serif;
      background-color: $color;
      box-shadow: 0px 0px 10px 0.2px rgba(0, 0, 0, 0.2) inset;
      color: rgb(36, 36, 36);
      //box-shadow: 0px 1px 2px rgba(166, 175, 195, 0.25);
      transition: 0.2s ease;

      &:hover {
        background-color: rgb(60, 60, 60);
        color: #fff;
        transition: 0.2s ease;
      }
    }
  }
</style>

<div class="nav-bar">
  {#each sections as section, index}
    <button class="boton" on:click={() => goToSection(index)}>{section.title}</button>
  {/each}
  <a href="#contacto" class="boton">Contacto</a>
</div>
