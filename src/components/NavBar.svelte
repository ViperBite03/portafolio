<script lang="ts">
  import type { ISection } from '../interfaces/ISection'

  export let sections: ISection[]
</script>

<style lang="scss">
  .nav-bar {
    background-color: rgb(255, 255, 255);
    height: fit-content;
    width: fit-content;
    z-index: 99;

    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;

    border-radius: 100px;
    padding: 15px 20px;
    left: 0;
    right: 0;
    top: 15px;
    margin: auto;

    a {
      cursor: pointer;
      padding: 7px 14px;
      border: none;
      border-radius: 15px;

      font-size: 13px;
      font-weight: bold;
      font-family: 'Poppins', sans-serif;
      background-color: white;
      color: rgb(36, 36, 36);
      box-shadow: 0px 1px 2px rgba(166, 175, 195, 0.25);
      transition: 0.2s ease;

      &:hover {
        background-color: rgb(36, 36, 36);
        color: #fff;
        transition: 0.2s ease;
      }
    }
  }
</style>

<div class="nav-bar">
  {#each sections as section}
    <a href="#{section.url}">{section.title}</a>
  {/each}
</div>
