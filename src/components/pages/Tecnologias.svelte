<script lang="ts">
  import type { ITecnologia } from './../../interfaces/ITecnologia.ts'

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
</style>

<div class="tecnologias">
  {#each tecnologias as tecnologia}
    <div class="tecnologia">
      <img src={tecnologia.img} alt="css" />
      <div class="label">{tecnologia.title}</div>
    </div>
  {/each}
</div>
