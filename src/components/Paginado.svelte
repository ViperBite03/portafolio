<script lang="ts">
  import type { IIdioma } from './../interfaces/IIdioma.ts'
  import type { ISection } from './../interfaces/ISection.ts'
  import Page from './Page.svelte'
  import { onMount } from 'svelte'

  export let sections: ISection[]

  let HTMLPages: HTMLElement

  const idiomas: IIdioma[] = [
    { title: 'Spanish', level: 'Native', color: '#4BC0FD', progress: 100 },
    { title: 'Catalan', level: 'Bilingual', color: '#9D6CFF', progress: 85 },
    { title: 'English', level: 'Advanced', color: '#00E175', progress: 75 },
  ]

  onMount(() => {
    const pages = [...HTMLPages.children]

    document.addEventListener('scroll', () => {
      pages.map((page: HTMLElement, i: number) => {
        if (window.scrollY > 931 + 300 * i) {
          page.style.transform = `translateY(${i * 25}px)`
          return
        }

        page.style.transform = `translateY(750px)`

        //console.log(window.scrollY, tope)
      })

      const tope: number = 931 + 300 * pages.length

      if (window.scrollY > tope) {
        console.log(window.scrollY, tope)
        HTMLPages.style.transform = `translateY(-${window.scrollY - tope}px)`
      }
    })
  })
</script>

<style lang="scss">
  .container {
    position: sticky;
    top: 0;
    height: 100vh;
    width: 100%;

    .text {
      font-size: 30px;
    }

    .idiomas {
      display: flex;
      justify-content: space-around;

      .idioma-title {
        font-size: 30px;
      }

      .bar {
        height: 30px;
        width: 300px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        position: relative;
        margin-top: 15px;
        border-radius: 30px;
        padding: 0 15px 0 15px;
        background-color: white;
        overflow: hidden;

        .tag {
          z-index: 1;
          color: white;
        }

        .name {
          z-index: 1;
        }

        .level {
          position: absolute;
          height: 30px;
          width: 300px;
          border-radius: 30px;
          transform: translateX(-15px);
        }
      }
    }

    :global(#sobre-mi) {
      transform: translateY(0) !important;
    }
  }
</style>

<div class="container" bind:this={HTMLPages}>
  <Page title={sections[0].title} id="sobre-mi">
    <div class="text">Se hacer botoncitos to majos y te pongo las tildes si te olvidas 👍.</div>
  </Page>

  <Page title={sections[1].title} id="estudios" />

  <Page title={sections[2].title} id="idiomas">
    <div class="idiomas">
      {#each idiomas as idioma}
        <div class="idioma">
          <div class="idioma-title">{idioma.title}</div>
          <div class="bar">
            <div class="tag">Level</div>
            <div class="name">{idioma.level}</div>
            <div class="level" style="background-color: {idioma.color}; width: calc({idioma.progress}% + 3px);"></div>
          </div>
        </div>
      {/each}
    </div>
  </Page>

  <Page title={sections[3].title} id="yo2" />
  <Page title={sections[4].title} id="yo2" />
  <Page title={sections[5].title} id="yo2" />
  <Page title={sections[6].title} id="yo2" />
</div>
