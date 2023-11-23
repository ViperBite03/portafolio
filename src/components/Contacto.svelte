<script lang="ts">
  import Form from './Form.svelte'
</script>

<style lang="scss">
  .footer {
    position: absolute;
    bottom: 0;
    transform: translateY(calc(75vh + 3031px));
    height: 75vh;
    width: 100%;
    background-color: aquamarine;
  }
</style>

<div class="footer">
  <Form />
</div>
