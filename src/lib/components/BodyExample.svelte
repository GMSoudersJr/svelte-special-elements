<script lang="ts">
  let entered = true;
  const handleMouseenter = (event: MouseEvent) => {
    entered = true;
  }
  const handleMouseleave = (event: MouseEvent) => {
    entered = false;
  }
  const handleMouseMove = (event: MouseEvent) => {
    coordinateX = event.clientX;
    coordinateY = event.clientY;
  }
  let coordinateX: number;
  let coordinateY: number;
</script>

<svelte:body
  on:mouseenter={handleMouseenter}
  on:mouseleave={handleMouseleave}
  on:mousemove={handleMouseMove}
/>

<div
  class="body_example example"
  class:entered={entered}
>
  {#if entered}
    {#if !coordinateX || !coordinateY}
    <p class="coordinates">Move the cursor</p>
    {:else}
    <p class="coordinates">{coordinateX},{coordinateY}</p>
    {/if}
  {/if}
</div>

<style>
  .body_example {
    width: 100px;
    height: 100px;
    border-radius: 5%;
    background-color: #FFF222;
    transition: all 0.5s ease-out;
    margin: auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .entered {
    background-color: #FFF;
    border-radius: 50%;
  }
</style>

