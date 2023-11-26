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

    .subtitle {
      font-size: 20px;
      font-weight: bold;
    }

    .content {
      height: fit-content;
      width: 100%;
      display: flex;
      justify-content: space-around;
      align-items: center;
      margin-top: 50px;

      .contact-info {
        .info-title {
          font-size: 20px;
        }

        .social {
          display: flex;
          flex-direction: column;
          text-align: center;
          gap: 10px;
          margin-top: 15px;

          a {
            height: fit-content;
            display: flex;
            align-items: center;

            .name {
              margin-left: 10px;
            }

            .icono {
              height: 25px;
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
      <span class="info-title">Información de contacto</span>
      <div class="social">
        {#each contactInfos as contactInfo}
          <a class="tlf" href={contactInfo.href}>
            <img class="icono" src={contactInfo.img} alt="" />
            <div class="name">{contactInfo.name}</div>
          </a>
        {/each}
      </div>
    </div>
    <div class="dsihfso">Miquel puto</div>
  </div>
</div>
