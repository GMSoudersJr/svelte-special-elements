<script lang="ts">
  import { page } from "$app/stores";
	import SelfExample from "$lib/components/SelfExample.svelte";
	import SlotExample from "$lib/components/SlotExample.svelte";
  import ComponentExample from "$lib/components/ComponentExample.svelte";
  import ElementExample from "$lib/components/ElementExample.svelte";
  import WindowExample from "$lib/components/WindowExample.svelte";
  import DocumentExample from "$lib/components/DocumentExample.svelte";
  import BodyExample from "$lib/components/BodyExample.svelte";

  interface Examples {
    [key: string]: typeof Page__SvelteComponent_;
  }

  const example: Examples = {
    self: SelfExample,
    slot: SlotExample,
    component: ComponentExample,
    element: ElementExample,
    window: WindowExample,
    document: DocumentExample,
    body: BodyExample,
  };

  $: specialElement = $page.params.specialElement;
</script>
<div class="background grid-container">
  <h1>{specialElement.toUpperCase()}</h1>
  <svelte:component this={example[specialElement]} />
</div>

<style>
  .grid-container {
    display: grid;
    grid-template-rows: min-content;
    row-gap: 1rem;
    padding-top: 1rem;
    padding-bottom: 1.618rem;
  }
</style>
