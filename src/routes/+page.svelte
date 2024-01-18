<script lang="ts">
</script>
<svelte:head>
  <title>
    Svelte Special Elements
  </title>
</svelte:head>
<div class="outer">
  <div class="inner">
    <h1>Exploring Svelte's Special Elements</h1>
    <p>Went through the docs and tried them all out</p>
  </div>
</div>

<style>
  .outer {
    padding: 2px;
    border-radius: 8px;
    display: grid;
    background: rgb(2,0,36);
    background: linear-gradient(215deg, rgba(2,0,36,1) 0%, rgba(203,43,213,0.915954415954416) 26%, rgba(0,212,255,1) 100%);
  }
  .inner {
    border-radius: 6px;
    background-color: white;
    padding: 1rem;
    display: grid;
    row-gap: 1rem;
  }
</style>
