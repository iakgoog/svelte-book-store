<script>
  import { createEventDispatcher } from 'svelte';
  import Button from './Button.svelte'
  export let bookTitle;
  export let bookPrice;
  export let bookDescription;

  const dispatch = createEventDispatcher();

  function purchaseBook() {
    dispatch("buy", bookTitle);
  }
</script>

<div>
  <h2>{bookTitle}</h2>
  <p>{bookPrice}</p>
  <p>{bookDescription}</p>
  <Button on:click={purchaseBook}>Buy</Button>
</div>

<style>
  div {
    margin: 1rem;
    padding: 1rem;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  }

  h1 {
    font-size: 1.25rem;
    margin: 0.25rem 0;
  }

  h2 {
    font-size: 1rem;
    margin: 0.25rem 0;
  }
  
  p {
    margin: 0.25rem 0;
  }

  button {
    font: larger;
    padding: 0.15rem 0.5rem;
    background-color: #1b1a1a;
    border: 1px solid aliceblue;
    cursor: pointer;
    color: white;
  }
</style>
