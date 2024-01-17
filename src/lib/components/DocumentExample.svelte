<script lang="ts">
	import SlotWidget from "./SlotWidget.svelte";

  function handleVisibility(event: Event) {
    console.log(document.visibilityState);
    if ( document.visibilityState === "hidden" ) {
      message = "Goodbye";
    } else {
      message = "Welcome Back!";
    }
  }

  let message = "Hello!";
</script>

<svelte:document
  on:visibilitychange={handleVisibility}
/>

<SlotWidget>
  <h1 slot="header">Document Visibility</h1>
  <p slot="disclaimer">This detects the document's visibility</p>
  <p slot="content">{message}</p>
</SlotWidget>

