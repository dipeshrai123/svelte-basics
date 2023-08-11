<script>
  export let count = 0
  $: countDouble = count * 2 // reactive declaration
  $: error = countDouble >= 10

  function increment() {
    count += 1
  }

  function decrement() {
    if (count <= 0) return
    count -= 1
  }
</script>

<div>
  <button on:click={decrement}>Decrement ( - )</button>
  <span>{count}</span>
  <button on:click={increment}>Increment ( + )</button>

  <div>
    <span>Double is: {countDouble}</span>
  </div>

  {#if error}
    <div class="error">ERROR! Don't cross 10</div>
  {/if}
</div>

<style>
  .error {
    color: red;
  }
</style>
