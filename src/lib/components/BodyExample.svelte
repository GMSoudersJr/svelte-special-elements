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
    background: rgba(0,212,255,1);
    transition: all 1s ease;
    margin: auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .entered {
    transform: rotate(360deg);
    border-radius: 50%;
  }
</style>
