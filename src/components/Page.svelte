<script lang="ts">
  export let id: string = ''
  export let title: string = 'Sobre mí'
  export let icon: string = ''
</script>

<style lang="scss">
  .page {
    position: absolute;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    max-height: 1000px;
    height: 87vh;
    //background-color: rgb(225 207 255);
    background-color: rgb(190 150 255);
    box-shadow: 0 -10px 25px -15px rgba(100, 100, 100, 0.25);
    border-radius: 20px;
    padding: 50px;
    left: 50px;
    right: 50px;
    bottom: 0;
    margin: auto;
    transition: 1s ease;
    transform: translateY(calc(100vh - 100vh / 5.5));

    .title {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 50px;

      .circle {
        height: 75px;
        width: 75px;
        border: 1px solid black;
        border-radius: 75px;
        display: flex;
        justify-content: center;
        align-items: center;

        img {
          height: 35px;
        }
      }

      .header {
        font-family: 'against', sans-serif;
        font-size: 70px;
      }
    }
  }
</style>

<div class="page" {id}>
  <div class="title">
    <div class="header">{title}</div>
    <div class="circle">
      <img src="{icon}.svg" alt="" />
    </div>
  </div>
  <div class="content">
    <slot><!-- optional fallback --></slot>
  </div>
</div>
