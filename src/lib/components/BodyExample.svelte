<script lang="ts">
  let entered = false;
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
  class:active={entered}
>
</div>

<style>
  .body_example {
    width: 100px;
    height: 100px;
    background-color: dodgerblue;
    margin: auto;
  }
  .active {
    background-color: black;
  }
</style>

