<script lang="ts">
  import type { ISection } from './../interfaces/ISection.ts'
  import Page from './Page.svelte'

  export let sections: ISection[]
</script>

<style lang="scss">
  .contenedor {
    position: relative;

    .paginado {
      position: sticky;
      top: 0;
      height: 100vh;
      width: 100%;
      z-index: 2;
      transition: 0.75s ease;

      /*@include notDesktop {
        //he tocado esto y ahora el footer (aka el contacto) ni se muestra :)
        height: 75vh;
      }*/

      .text {
        font-family: 'Poppins', sans-serif;
        font-size: 25px;
        text-wrap: balance;
      }

      :global(#sobre-mi) {
        transform: translateY(0) !important;
      }
    }
  }
</style>

<div class="contenedor">
  <div class="paginado">
    {#each sections as section}
      <Page title={section.title} id={section.url} icon={section.icon}>
        <svelte:component this={section.component} />
      </Page>
    {/each}
  </div>
</div>
