<script lang="ts">
  import type { IInfo } from './../interfaces/IInfo.ts'
  const contactInfos: IInfo[] = [
    {
      title: 'Github',
      name: 'ViperBite03',
      img: './../public/Github.svg',
      href: 'https://github.com/ViperBite03',
    },
    {
      title: 'Linkedin',
      name: 'Laia Martin',
      img: './../public/Linkedin.svg',
      href: 'https://www.linkedin.com/in/laia-martin-de-la-660031280/',
    },
    {
      title: 'Email',
      name: 'lamadelafu03@gmail.com',
      img: './../public/Carta.svg',
      href: 'mailto:lamadelafu03@gmail.com',
    },
    {
      title: 'tlf',
      name: '671 707 263',
      img: './../public/Phone.svg',
      href: '',
    },
  ]
</script>

<style lang="scss">
  $color: rgb(225 207 255);

  .footer {
    position: absolute;
    bottom: 0;
    transform: translateY(calc(75vh + 3031px));
    height: 75vh;
    width: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
    color: white;
    font-family: 'Poppins', sans-serif;

    .title {
      font-family: 'against', sans-serif;
      margin-top: 50px;
      font-size: 75px;
      color: white;
    }

    .content {
      height: fit-content;
      width: 100%;
      display: flex;
      justify-content: space-around;
      padding: 0 275px;
      align-items: center;
      margin-top: 50px;
      position: relative;

      .picture {
        max-width: 300px;
      }

      .rectangle {
        position: absolute;
        height: 200px;
        width: 1000px;
        border-radius: 20px;
        z-index: -1;
        //background-color: $color;
        //opacity: 0.7;

        box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
        backdrop-filter: blur(2px);
        border: 1px solid rgba(255, 255, 255, 0.2);
      }

      .contact-info {
        .social {
          display: flex;
          flex-direction: column;
          text-align: center;
          font-size: 20px;
          gap: 10px;
          margin-left: 20px;

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
              margin-left: 15px;
            }

            .icono {
              height: 35px;
              filter: invert(1);
            }
          }
        }
      }
    }
  }
</style>

<div class="footer" id="contacto">
  <div class="title">Contacto</div>
  <div class="subtitle">¡Ponte en contacto conmigo!</div>
  <div class="content">
    <div class="contact-info">
      <div class="social">
        {#each contactInfos as contactInfo}
          <a class="tlf" href={contactInfo.href} target="_blank">
            <img class="icono" src={contactInfo.img} alt="" />
            <div class="name">{contactInfo.name}</div>
          </a>
        {/each}
      </div>
    </div>
    <img class="picture" src="./../public/chibi-me.png" alt="" />
    <div class="rectangle"></div>
  </div>
</div>
