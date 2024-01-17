<script lang="ts">
  let entered = true;
  const handleMouseenter = (event: MouseEvent) => {
    entered = true;
  }
  const handleMouseleave = (event: MouseEvent) => {
    entered = false;

  }
</script>

<svelte:body
  on:mouseenter={handleMouseenter}
  on:mouseleave={handleMouseleave}
/>

<div
  class="body_example"
  class:entered={entered}
>
</div>

<style>
  .body_example {
    width: 100px;
    height: 100px;
    background-color: dodgerblue;
    transition: all 1s ease-out;
    margin: auto;
  }
  .entered {
    background-color: black;
    border-radius: 50%;
  }
</style>

