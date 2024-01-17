<script>
	import SlotWidget from "./SlotWidget.svelte";
</script>

<SlotWidget>
  <h1 slot="header">Specify per-component compiler options</h1>
  <p slot="disclaimer">Have not found much use for this, yet</p>
  <p slot="content">Will be handy for custom elements in the future</p>
</SlotWidget>
