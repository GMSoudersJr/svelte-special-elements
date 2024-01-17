<script>
	import SlotWidget from "./SlotWidget.svelte";

</script>

<SlotWidget>
  <h1 slot="header">Inserts elements into document.head</h1>
  <p slot="disclaimer">Checkout out the tab name</p>
  <p slot="content">It has been changing the entire time</p>
</SlotWidget>
