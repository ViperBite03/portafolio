<script lang="ts"></script>

<div class="nav-bar">
  <button id="boutme">Boutme</button>
  <button id="boutme">Boutme</button>
  <button id="boutme">Boutme</button>
  <button id="boutme">Boutme</button>
  <button id="boutme">Boutme</button>
</div>

<style lang="scss">
  .nav-bar {
    background-color: rgb(255, 255, 255);
    height: fit-content;
    width: fit-content;

    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;

    border-radius: 100px;
    padding: 14px 35px;
    left: 0;
    right: 0;
    top: 15px;
    margin: auto;

    button {
      cursor: pointer;
      padding: 7px 14px;
      border: none;
      border-radius: 15px;

      font-size: 15px;
      background-color: white;
      color: black;
      box-shadow: 0px 1px 2px rgba(166, 175, 195, 0.25);
      transition: 0.2s ease;

      &:hover {
        background-color: #1e293b;
        color: #fff;
        transition: 0.2s ease;
      }
    }
  }
</style>
