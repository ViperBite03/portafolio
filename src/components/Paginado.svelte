<script lang="ts">
  import Page from './Page.svelte'
  export let buttons
  import { onMount } from 'svelte'

  let HTMLPages

  onMount(() => {
    const pages = [...HTMLPages.children]

    document.addEventListener('scroll', (event) => {
      pages.map((page, i) => {
        if (window.scrollY > 931 + 300 * i) {
          page.style.transform = `translateY(${i * 25}px)`
          return
        }

        console.log(window.scrollY)
        page.style.transform = `translateY(750px)`
      })
    })
  })
</script>

<style lang="scss">
  .container {
    position: sticky;
    top: 0;
    height: 100vh;
    width: 100%;

    .text {
      font-size: 30px;
    }

    :global(#yo1) {
      transform: translateY(0) !important;
    }
  }
</style>

<div class="container" bind:this={HTMLPages}>
  <Page title={buttons[0].title} id="yo1">
    <div class="text">
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis eaque ab rem ex, dolorum aliquam libero voluptatum unde illum quisquam
      voluptas laboriosam veniam quaerat eius quod sunt incidunt quidem odio?
    </div>
  </Page>

  <Page title={buttons[1].title} id="yo2" />
  <Page title={buttons[2].title} id="yo2" />
  <Page title={buttons[3].title} id="yo2" />
  <Page title={buttons[4].title} id="yo2" />
  <Page title={buttons[5].title} id="yo2" />
  <Page title={buttons[6].title} id="yo2" />
  <Page title={buttons[7].title} id="yo2" />
</div>
