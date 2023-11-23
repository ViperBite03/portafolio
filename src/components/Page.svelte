<script lang="ts">
  export let id: string = ''
  export let title: string = 'Sobre mí'
</script>

<style lang="scss">
  .page {
    position: absolute;
    height: 87.5%;
    width: 95%;
    display: flex;
    flex-direction: column;
    background-color: rgb(225 207 255);
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
      font-family: 'against', sans-serif;
      font-size: 70px;
      margin-bottom: 50px;
    }
  }
</style>

<div class="page" {id}>
  <div class="title">{title}</div>
  <div class="content">
    <slot><!-- optional fallback --></slot>
  </div>
</div>
