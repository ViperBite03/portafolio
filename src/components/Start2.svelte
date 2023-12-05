<script lang="ts">
  import type { IInfo } from './../interfaces/IInfo.ts'
  const contactInfos: IInfo[] = [
    {
      title: 'Github',
      name: 'ViperBite03',
      img: 'Github.svg',
      href: 'https://github.com/ViperBite03',
    },
    {
      title: 'Linkedin',
      name: 'Laia Martin',
      img: 'Linkedin.svg',
      href: 'https://www.linkedin.com/in/laia-martin-de-la-660031280/',
    },
  ]
</script>

<style lang="scss">
  $color: rgb(97, 45, 170);

  .portada {
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
    width: 100%;
    height: 100vh;

    .rectangle {
      height: 75%;
      width: 50%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 50px;

      border-radius: 20px 0 0 20px;
      background-color: rgb(190 150 255);
      box-shadow: -5px 0px 15px 0px rgba(0, 0, 0, 0.5);

      .images {
        position: relative;
        border-radius: 20px;
        width: 100%;
        height: 100%;
        overflow: hidden;

        max-height: 500px;
        max-width: 500px;

        .front,
        .back {
          width: 100%;
          height: 100%;
          position: absolute;
        }
      }

      .contacto {
        display: flex;
        text-align: center;
        font-size: 20px;
        gap: 25px;
        margin-left: 20px;
        font-family: 'Poppins', sans-serif;
        color: white;

        a {
          height: fit-content;
          width: fit-content;
          display: flex;
          align-items: center;
          transition: 0.2s ease;

          &:hover {
            color: #2fe7c0;

            .icono {
              transform: scale(1.2);
              transition: 0.2s ease;
            }
          }

          .name {
            margin-left: 5px;
          }

          .icono {
            height: 35px;
            filter: invert(1);
          }
        }
      }
    }

    .texto {
      display: flex;
      flex-direction: column;
      justify-content: center;
      height: 100%;
      margin-left: 100px;
      color: white;
      z-index: 2;

      .title {
        font-family: 'against', sans-serif;
        text-shadow: 5px 5px 10px rgba(0, 0, 0, 0.5);
        font-size: 225px;
        text-align: left;
        max-width: 750px;
      }

      .subtitle {
        font-family: 'poppins', sans-serif;
        font-size: 35px;
      }
    }
  }
</style>

<div class="portada">
  <div class="texto">
    <div class="title">Laia Martin</div>
    <div class="subtitle">¡Bienvenido a mi portafolio!</div>
  </div>
  <div class="rectangle">
    <div class="images">
      <img class="front" src="https://cdn.pixabay.com/photo/2017/01/25/17/35/picture-2008484_1280.png" alt="" />
      <img class="back" src="https://cdn.pixabay.com/photo/2017/01/25/17/35/picture-2008484_1280.png" alt="" />
    </div>
    <div class="contacto">
      <a href={contactInfos[0].href} target="_blank">
        <img class="icono" src={contactInfos[0].img} alt="" />
        <div class="name">{contactInfos[0].name}</div>
      </a>
      <a href={contactInfos[1].href} target="_blank">
        <img class="icono" src={contactInfos[1].img} alt="" />
        <div class="name">{contactInfos[1].name}</div>
      </a>
    </div>
  </div>
</div>
