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
    display: flex;
    align-items: center;
    flex-direction: column;
    //background-color: aquamarine;

    .contact {
      font-family: 'against', sans-serif;
      margin-top: 50px;
      font-size: 75px;
      color: white;
    }
  }
</style>

<div class="footer">
  <div class="contact">Contacto</div>
  <Form />
</div>
