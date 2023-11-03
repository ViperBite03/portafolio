<script lang="ts">
  const title = "I'm Laia";
  import NavBar from "./NavBar.svelte";
</script>

<div class="start">
  <NavBar />
  <div class="glass">
    <div class="title">{title}</div>
  </div>
</div>

<style lang="scss">
  .start {
    height: 100vh;
    width: 100%;
    position: relative;
    display: flex;
    align-items: center;

    .glass {
      width: 100%;
      height: 50%;

      background: rgba(255, 255, 255, 0.13);
      box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
      backdrop-filter: blur(2px);
      border: 1px solid rgba(255, 255, 255, 0.2);

      display: flex;
      justify-content: center;
      align-items: center;

      .title {
        font-family: "against", sans-serif;

        background-clip: text;
        -webkit-background-clip: text;
        background-image: url(https://i.pinimg.com/originals/d8/7e/e3/d87ee381e69fc49b0686855f65df920c.jpg);
        background-size: cover;
        background-position: center;

        color: transparent;
        font-size: 125px;
      }
    }
  }
</style>
