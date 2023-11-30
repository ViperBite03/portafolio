<script lang="ts">
  export let id: string = ''
  export let title: string = 'Sobre mí'
  export let icon: string = ''
</script>

<style lang="scss">
  .page {
    position: absolute;
    height: 87.5%;
    width: 95%;
    display: flex;
    flex-direction: column;
    //background-color: rgb(225 207 255);
    background-color: rgb(190 150 255);
    box-shadow: 0 -10px 25px -15px rgba(100, 100, 100, 0.25);
    border-radius: 20px;
    padding: 50px;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    transition: 1s ease;
    transform: translateY(750px);

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
      <img src="./../public/{icon}.svg" alt="" />
    </div>
  </div>
  <div class="content">
    <slot><!-- optional fallback --></slot>
  </div>
</div>
