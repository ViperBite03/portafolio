<script lang="ts">
  import type { ITecnologia } from './../interfaces/ITecnologia.ts'
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

  const tecnologias: ITecnologia[] = [
    { title: 'CSS', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg' },
    { title: 'HTML5', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg' },
    { title: 'JS', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg' },
    { title: 'TS', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg' },
    { title: 'Sass', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sass/sass-original.svg' },
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
        HTMLPages.style.transform = `translateY(-${(window.scrollY - tope) / 2}px)`
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
      font-family: 'Poppins', sans-serif;
      font-size: 30px;
    }

    .idiomas {
      display: flex;
      justify-content: space-around;

      .idioma {
        transform: scale(1.2);

        .idioma-title {
          font-size: 30px;
        }

        .bar {
          height: 15px;
          width: 300px;
          position: relative;
          display: flex;
          align-items: center;
          margin-top: 15px;

          border-radius: 30px;

          background-color: white;
          overflow: hidden;

          .tag {
            font-family: 'Poppins', sans-serif;
            margin-left: 5px;
            font-size: 12px;
            z-index: 1;
          }

          .level {
            position: absolute;
            height: 15px;
            width: 300px;
            border-radius: 30px;
          }
        }
      }
    }

    .tecnologias {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 50px;

      .tecnologia {
        font-family: 'Poppins', sans-serif;
        display: flex;
        flex-direction: column;
        align-items: center;

        img {
          margin-top: 50px;
          margin-bottom: 10px;
          width: 75px;
          height: 75px;
        }
      }
    }

    :global(#sobre-mi) {
      transform: translateY(0) !important;
    }
  }
</style>

<div class="container" bind:this={HTMLPages}>
  <Page title={sections[0].title} id={sections[0].url}>
    <div class="text">Se hacer botoncitos to majos y te pongo las tildes si te olvidas 👍.</div>
  </Page>

  <Page title={sections[1].title} id={sections[1].url} />

  <Page title={sections[2].title} id={sections[2].url}>
    <div class="idiomas">
      {#each idiomas as idioma}
        <div class="idioma">
          <div class="idioma-title">{idioma.title}</div>
          <div class="bar">
            <div class="tag">{idioma.level}</div>
            <div class="level" style="background-color: {idioma.color}; width: calc({idioma.progress}% + 3px);"></div>
          </div>
        </div>
      {/each}
    </div>
  </Page>

  <Page title={sections[3].title} id={sections[3].url} />
  <Page title={sections[4].title} id={sections[4].url}>
    <div class="tecnologias">
      {#each tecnologias as tecnologia}
        <div class="tecnologia">
          <img src={tecnologia.img} alt="css" />
          <div class="label">{tecnologia.title}</div>
        </div>
      {/each}
    </div>
  </Page>
  <Page title={sections[5].title} id={sections[5].url} />
  <Page title={sections[6].title} id={sections[6].url} />
</div>
