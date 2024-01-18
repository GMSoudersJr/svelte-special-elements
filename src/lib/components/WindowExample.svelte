<script lang="ts">
  function handleKeydown(event: KeyboardEvent) {
    keyPressed = event.key;
    if ( keyPressed === " " ) {
      keyPressed = "Space";

    }
  }
  function handleKeyup(event: KeyboardEvent) {
    setTimeout(() => {
      keyPressed = undefined;
    }, 750)
  }
  let keyPressed: string | undefined;
</script>

<svelte:window
  on:keydown={handleKeydown}
  on:keyup={handleKeyup}
/>

<div class="example">
 <h4>press any key on the keyboard</h4>
</div>

<div class="key_press">
 {#if keyPressed}
   <h1 class="key">{keyPressed}</h1>
 {/if}
</div>

<style>
  .key_press {
    margin: auto;
    background-color: rgba(0,212,255,1);
    filter: brightness(90%);
    height: 120px;
    width: 120px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .key {
    transform: scale(1.2);
  }
</style>
