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
   <h1>{keyPressed}</h1>
 {/if}
</div>

<style>
  .key_press {
    margin: auto;
    background-color: #F9F9A9;
    height: 100px;
    width: 100px;
    border-radius: 6px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
