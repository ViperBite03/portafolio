<script lang="ts">
  import type { ITecnologia } from './../interfaces/ITecnologia.ts'
  import type { IIdioma } from './../interfaces/IIdioma.ts'
  import type { ISection } from './../interfaces/ISection.ts'
  import Page from './Page.svelte'

  export let sections: ISection[]

  const idiomas: IIdioma[] = [
    { title: 'Spanish', level: 'Native', color: '#4BC0FD', progress: 100 },
    { title: 'Catalan', level: 'Bilingual', color: '#9D6CFF', progress: 85 },
    { title: 'English', level: 'Advanced', color: '#00E175', progress: 75 },
  ]

  const tecnologias: ITecnologia[] = [
    { title: 'Sass', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sass/sass-original.svg' },
    { title: 'CSS', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg' },
    { title: 'HTML5', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg' },
    { title: 'JavaScript', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg' },
    { title: 'TypeScript  ', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg' },
    { title: 'Svelte', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/svelte/svelte-original.svg' },
    { title: 'Git', img: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg' },
    { title: 'Astro', img: 'https://www.svgrepo.com/show/373446/astro.svg' },
  ]
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

      @include notDesktop {
        //he tocado esto y ahora el footer (aka el contacto) ni se muestra :)
        height: 75vh;
      }

      .text {
        font-family: 'Poppins', sans-serif;
        font-size: 25px;
        text-wrap: balance;
      }

      .sobre-mi {
        display: flex;
        justify-content: space-between;
        padding: 0 25px;

        .text {
          max-width: 750px;
          padding: 25px 0;
        }

        .picture {
          max-width: 500px;
          margin-right: 25px;
        }
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

            background-color: inherit;
            box-shadow: 0px 0px 10px 0.2px rgba(0, 0, 0, 0.2) inset;
            overflow: hidden;

            .tag {
              font-family: 'Poppins', sans-serif;
              margin-left: 5px;
              font-size: 12px;
            }

            .level {
              position: absolute;
              z-index: -1;
              height: 14px;
              width: 300px;
              //border-radius: 30px;
            }
          }
        }
      }

      .tecnologias {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
        align-items: center;
        justify-items: center;
        max-width: 1200px;
        margin: auto;
        width: 100%;
        gap: 15px;

        .tecnologia {
          font-family: 'Poppins', sans-serif;
          display: flex;
          flex-direction: column;
          align-items: center;

          img {
            margin-top: 100px;
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
  }
</style>

<div class="contenedor">
  <div class="paginado">
    <Page title={sections[0].title} id={sections[0].url} icon={sections[0].icon}>
      <div class="sobre-mi">
        <span class="text" contenteditable
          >Se hacer botoncitos to majos y te pongo las tildes si te olvidas 👍. También soy programadora porno.</span
        >
        <img class="picture" src="https://cdn.pixabay.com/photo/2017/01/25/17/35/picture-2008484_1280.png" alt="" />
      </div>
    </Page>

    <Page title={sections[1].title} id={sections[1].url} icon={sections[1].icon}>
      <div class="estudios"></div>
    </Page>

    <Page title={sections[2].title} id={sections[2].url} icon={sections[2].icon}>
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

    <Page title={sections[3].title} id={sections[3].url} icon={sections[3].icon}>
      <div class="text">Se hacer botoncitos to majos y te pongo las tildes si te olvidas 👍. También soy programadora porno :).</div>
    </Page>
    <Page title={sections[4].title} id={sections[4].url} icon={sections[4].icon}>
      <div class="tecnologias">
        {#each tecnologias as tecnologia}
          <div class="tecnologia">
            <img src={tecnologia.img} alt="css" />
            <div class="label">{tecnologia.title}</div>
          </div>
        {/each}
      </div>
    </Page>
    <Page title={sections[5].title} id={sections[5].url} icon={sections[5].icon} />
    <Page title={sections[6].title} id={sections[6].url} icon={sections[6].icon}>
      <div class="text">Se hacer botoncitos to majos y te pongo las tildes si te olvidas 👍. También soy programadora porno :).</div>
    </Page>
  </div>
</div>
