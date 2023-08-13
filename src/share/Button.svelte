<script>
  export let type = 'primary';
  export let flat = false;
  export let inverse = false;
</script>

<button class={type}>
  <slot></slot>
</button>

<style>
   button {
    padding: 10px 20px;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-in-out;
    width: 100%;
  }

  button:hover {
    background-color: #0056b3;
  }

  .primary {
    background-color: orange;
  }

  .secondary {
    background-color: grey;
  }
</style>
