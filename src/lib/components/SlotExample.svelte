<script>
	import SlotWidget from "./SlotWidget.svelte";
</script>

<SlotWidget />

<SlotWidget>
  <h1 slot="header">Header via Named Slot</h1>
  <p slot="content">Content via named slot</p>
</SlotWidget>

<SlotWidget>
  <h1 slot="header">Header via Named Slot</h1>
  <p slot="content">Content and Footer via named slot</p>
  <p slot="footer">Copyright (c) 2024 Gerald Souders</p>
</SlotWidget>

<SlotWidget>
  <h1 slot="header">Header via Named Slot</h1>
  <p slot="disclaimer">Disclaimer via named slot</p>
  <p slot="content">Content and Footer via named slot</p>
  <p slot="footer">Copyright (c) 2024 Gerald Souders</p>
</SlotWidget>

<style>
</style>
