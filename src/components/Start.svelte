<script lang="ts">
</script>

<style lang="scss">
  .start {
    height: 100vh;
    width: 100%;
    position: relative;
    display: flex;
    align-items: center;

    .glass {
      z-index: 1;
      width: 100%;
      height: 50%;

      //background: rgba(0, 0, 0, 0.15);
      box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
      backdrop-filter: blur(5px);
      border: 1px solid rgba(255, 255, 255, 0.2);

      display: flex;
      justify-content: right;
      align-items: center;

      .title {
        font-family: 'against', sans-serif;
        color: rgb(225 207 255);
        font-size: 150px;
        max-width: 750px;
        text-align: right;

        margin-right: 100px;
      }
    }
  }
</style>

<div class="start">
  <div class="glass">
    <div class="title">Laia Martin</div>
  </div>
</div>
