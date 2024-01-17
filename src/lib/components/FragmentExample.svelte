<script>
	import SlotWidget from "./SlotWidget.svelte";

</script>

<SlotWidget>
  <h1 slot="header">Widget without <code>&lt;svelte:fragment&gt;</code></h1>
  <p slot="disclaimer">
    This footer is wrapped in a <code>&lt;p&gt;</code> element.
  </p>
  <p slot="content">
    Without <code>&lt;svelte:fragment&gt;</code>, must wrap code in a DOM element.
  </p>
  <p slot="footer">Copyright (c) 2024 Gerald Souders</p>
</SlotWidget>

<SlotWidget>
  <h1 slot="header">Widget with <code>&lt;svelte:fragment&gt;</code></h1>
  <p slot="disclaimer">
    This footer is wrapped in a <code>&lt;svelte:fragment&gt;</code> element.
  </p>
  <p slot="content">
    With <code>&lt;svelte:fragment&gt;</code>, the layout stays intact.
  </p>
  <svelte:fragment slot="footer">
    <p>All rights reserved.</p>
    <p>Copyright (c) 2024 Gerald Souders</p>
  </svelte:fragment>
</SlotWidget>

<style>
</style>
