<script lang="ts">
  import type { IIdioma } from './../interfaces/IIdioma.ts'

  const idiomas: IIdioma[] = [
    { title: 'Spanish', level: 'Native', color: '#4BC0FD', progress: 100 },
    { title: 'Catalan', level: 'Bilingual', color: '#9D6CFF', progress: 85 },
    { title: 'English', level: 'Advanced', color: '#00E175', progress: 75 },
  ]
</script>

<style lang="scss">
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
</style>

<div></div>

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
